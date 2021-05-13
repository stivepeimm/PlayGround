Hello 我是 大粽子

5.1小长假的节后综合征你缓过来没？【瞪眼】

### 一点点絮叨

大家都知道我focus在一个开源项目上，虽然出了商业版本，但说实话我对开源项目的质量很不满意，咱不说之前的各种因素不提，后面我们已经制定计划要升级框架，用微服务的方式构建Java应用。敬请长远期待。

为什么说是絮叨，我们项目中用到了nginx做图片服务的功能，也就是开启静态服务，可以http访问资源文件。

但个别童鞋可能之前没使用过等等就会出现各种莫名其妙的问题，其实网站本身就是一个静态服务。简单来讲我们将写好的html文件（可能是打包后生成）copy到网站，浏览器通过http访问会自动解析html而形成界面。

这样将是不是很简单，只是现在换个文件，将原来的html换成文件，可能是图片，文档或者视频等等 有点像对象存储服务。一样的道理。

为什么说是絮叨，因为围绕着这个话题我之前专门写了一次文档，但新加入或者漏看的同学就会有各种问题。

你想想5.1假期我在陪家人的时间里，**坐在金丝峡的山谷中**给大家回复关于nginx静态服务上传图片的问题，是不是画风很美【狗头】。

[nginx做图片服务安全么？戳这里](https://mp.weixin.qq.com/s/rcp3PgYKxeonYe_obHIczQ)

### 上菜

我就以最常用的两种实现方式，再次介绍下实现方式和具体配置。其他的http服务一样的实现原理，顶多也是配置区别，对应找下文档都是能实现的，这里就以nginx 和 tomcat 为例

### nginx配置方式

先看下基本配置节点说明文档 (电脑阅读体验佳)

~~~shell
########### 每个指令必须有分号结束。#################
#user administrator administrators;  #配置用户或者组，默认为nobody nobody。
#worker_processes 2;  #允许生成的进程数，默认为1
#pid /nginx/pid/nginx.pid;   #指定nginx进程运行文件存放地址
error_log log/error.log debug;  #制定日志路径，级别。这个设置可以放入全局块，http块，server块，级别以此为：debug|info|notice|warn|error|crit|alert|emerg
events {
    accept_mutex on;   #设置网路连接序列化，防止惊群现象发生，默认为on
    multi_accept on;  #设置一个进程是否同时接受多个网络连接，默认为off
    #use epoll;      #事件驱动模型，select|poll|kqueue|epoll|resig|/dev/poll|eventport
    worker_connections  1024;    #最大连接数，默认为512
}
http {
    include       mime.types;   #文件扩展名与文件类型映射表
    default_type  application/octet-stream; #默认文件类型，默认为text/plain
    #access_log off; #取消服务日志    
    log_format myFormat '$remote_addr–$remote_user [$time_local] $request $status $body_bytes_sent $http_referer $http_user_agent $http_x_forwarded_for'; #自定义格式
    access_log log/access.log myFormat;  #combined为日志格式的默认值
    sendfile on;   #允许sendfile方式传输文件，默认为off，可以在http块，server块，location块。
    sendfile_max_chunk 100k;  #每个进程每次调用传输数量不能大于设定的值，默认为0，即不设上限。
    keepalive_timeout 65;  #连接超时时间，默认为75s，可以在http，server，location块。

    upstream mysvr {   
      server 127.0.0.1:7878;
      server 192.168.10.121:3333 backup;  #热备
    }
    error_page 404 https://www.baidu.com; #错误页
    server {
        keepalive_requests 120; #单连接请求上限次数。
        listen       4545;   #监听端口
        server_name  127.0.0.1;   #监听地址       
        location  ~*^.+$ {       #请求的url过滤，正则匹配，~为区分大小写，~*为不区分大小写。
           #root path;  #根目录
           #index vv.txt;  #设置默认页
           proxy_pass  http://mysvr;  #请求转向mysvr 定义的服务器列表
           deny 127.0.0.1;  #拒绝的ip
           allow 172.18.5.54; #允许的ip           
        } 
    }
}
~~~

今天着重讲这里 root 的配置

![](https://gitee.com/stivepeim/img4mk/raw/master/20210507223643.png)

Mac 也好 windows 也好对应的配置是一样的，唯独不一样的就是路径了，这里我以本地mac为例

我的nginx资源配置

![一部分配置截图](https://gitee.com/stivepeim/img4mk/raw/master/20210507224417.png)

实际访问效果

![](https://gitee.com/stivepeim/img4mk/raw/master/20210507224908.png)

### tomcat配置方式

#### 方式1 都不用修改

直接在webapps--》ROOT --》中添加自己的资源文件即可 如下图操作，这也是tomcat默认的部署文档地址。

![](https://gitee.com/stivepeim/img4mk/raw/master/20210507225812.png)

#### 方式2 修改配置文件 需要修改两个配置文件

conf 目录下找到 server.xml 修改如下图

![](https://gitee.com/stivepeim/img4mk/raw/master/20210507230910.png)

同级目录找到web.xml 修改对应的监听 以动态添加后可直接访问

![](https://gitee.com/stivepeim/img4mk/raw/master/20210507231058.png)

![](/Users/stivepeim/Library/Application Support/typora-user-images/image-20210507231139978.png)

可以愉快的玩耍了

#### 总结

上面是分别是nginx 和 tomcat 两种方式配置静态服务，如果你实在懒得找或者怕敲错（尤其是xml配置）

可以在公众号回复 **静态服务** 获取对应配置文件

上面只是用两个工具运行起来了静态服务，但是大多数应用程序并不知道你的静态服务种类是什么以及配置的磁盘地址是哪些，所以对应在程序中配置以下两个

1：告诉程序服务怎么访问

2：告诉程序服务在哪个文件夹下

### 了解更多关于电商服务程序可以访问历史文件

- [【开源电商基础介绍】了解一个电商基础](https://mp.weixin.qq.com/s/d7TAOzcCtjpNwqqAeU8ftA)
- [【开源电商快速浏览】不会运行没关系，跟着文档找节奏](https://mp.weixin.qq.com/s/DrRn0Zx-WPMe_Ocg7Oo1MA)
- [【开源电商服务部署】域名+后台服务](https://mp.weixin.qq.com/s/s5CqqlcLrDsLY8NEU47_4w)
- [【开源电商宝塔】宝塔使用和站点创建](https://mp.weixin.qq.com/s/2TDLMvmZM1EXDnJ39kR6Qw)
- [【开源电商表单工具】减少表单重复开发，拖拉拽搞定](https://mp.weixin.qq.com/s/1an2WYS10rwtWzQobs34kQ)
- [【开源电商无限极分类设计】前同事留下的经典功能](https://mp.weixin.qq.com/s/e8TNaRpdX71C74O3BtBa7A)
- [【开源电商基本功能介绍】组合数据](https://mp.weixin.qq.com/s/naRUwGHY1bOn9UepeOErTg)
- [【开源电商快速部署服务】基于宝塔](https://mp.weixin.qq.com/s/VZ5zCuScA-zZzZCYxfxByA)
- [一个标准的Springboot —+ vue + uniapp 的商城怎么部署](https://mp.weixin.qq.com/s/eFTr3-3w_5vA5veCdyCzZw)