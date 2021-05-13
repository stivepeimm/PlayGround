Hello 我是 西北大粽子

### 如题 nginx做图片服务安全吗？

首先说下nginx是做什么的。

![官方说法](https://gitee.com/stivepeim/img4mk/raw/master/20210429233823.png)

## 推荐阅读

- [【开源电商基础介绍】了解一个电商基础](https://mp.weixin.qq.com/s/d7TAOzcCtjpNwqqAeU8ftA)
- [【开源电商快速浏览】不会运行没关系，跟着文档找节奏](https://mp.weixin.qq.com/s/DrRn0Zx-WPMe_Ocg7Oo1MA)
- [【开源电商服务部署】域名+后台服务](https://mp.weixin.qq.com/s/s5CqqlcLrDsLY8NEU47_4w)
- [【开源电商宝塔】宝塔使用和站点创建](https://mp.weixin.qq.com/s/2TDLMvmZM1EXDnJ39kR6Qw)
- [【开源电商表单工具】减少表单重复开发，拖拉拽搞定](https://mp.weixin.qq.com/s/1an2WYS10rwtWzQobs34kQ)
- [【开源电商无限极分类设计】前同事留下的经典功能](https://mp.weixin.qq.com/s/e8TNaRpdX71C74O3BtBa7A)
- [【开源电商基本功能介绍】组合数据](https://mp.weixin.qq.com/s/naRUwGHY1bOn9UepeOErTg)
- [【开源电商快速部署服务】基于宝塔](https://mp.weixin.qq.com/s/VZ5zCuScA-zZzZCYxfxByA)
- [一个标准的Springboot —+ vue + uniapp 的商城怎么部署](https://mp.weixin.qq.com/s/eFTr3-3w_5vA5veCdyCzZw)

### 一点点历史

其实现在百分之九十的公司和朋友都在用nginx  不做后端开发的同学可能都不知道tom猫，

是的就是**tomcat**，还有**Apache**，**WebSphere**， **IIS**， **WebLogic** 等等

其实真正开发中我指给一个老项目是配过WebSphere  IIS 微软家族用的多 WebLogic 基本上很少用了。

用的最多的应该算 **nginx** 和 **tomcat** 当然作为使用习惯其实还有偏好，比如前端开发同学nginx可能玩的很溜，Java开发tomcat那是不了的，当然你可以用别的，或者不是web开发肯定用不到。

### 正题

先了解个问题，云服务提供商的OSS是什么？

对象存储(Object Storage Service,简称*OSS*) 

也就是存储文件的服务，每个厂商可能名称不统一，但实质都是一样的。怎么实现的呢？其实也就是http服务挂载磁盘。

这个服务最大的就是存储和流量了，存数据得占用磁盘，下载上传得浪费流量，基本上都是这两个收费项目构成一个对象存储服务。当然每个厂商对应还有高阶服务，比如安全，转移，备份等等也是收费项。

### 我们自己开发过程中怎么实现这个服务 以nginx为例

这是我的一部分配置

~~~shell
server {
   	listen	9999;
   	server_name localhost;

	#配置跨域

        add_header Access-Control-Allow-Origin *;
        add_header Access-Control-Allow-Headers X-Requested-With;
        add_header Access-Control-Allow-Methods GET,POST,OPTIONS;

	location / {
		#开启授权登录
		auth_basic "Auth";
		# 授权登录文件 包涵名称和密码 生成方式看下方
		auth_basic_user_file /usr/local/etc/nginx/htpasswd/htpwd_dazongzi;
		root /Users/stivepeim/Desktop/crmebApplication/app/crmebimage/;
		autoindex on;
	}

   	#location ~ .*\.(gif|jpg|jpeg|png|bmp|swf|pem|p12)$
   	# {
   	#	expires      30d;
   	#}
    }
~~~



### 为nginx生成用户和密码

![生成Nginx密码](https://gitee.com/stivepeim/img4mk/raw/master/20210429233833.png)

因为默认nginx没有开启用户限制 手动开启 使用htpasswd生成密码 没有命令可以自行安装下

~~~shell
yum install -y httpd-tools 
~~~



这样我们会给nginx服务开启用户限制以免被坏蛋搞怪，给你上传GB级别的垃圾或者exe shell什么的还是挺害怕的哈。

![初次登陆](https://gitee.com/stivepeim/img4mk/raw/master/20210429234224.png)

![愉快的玩耍吧](https://gitee.com/stivepeim/img4mk/raw/master/20210429234230.png)

要是经常读源码找文档的朋友看到这界面是不是很熟悉，nginx centos apache等开源文档就是这么搞得。

### 知识就想雪球，滚的越远才会越大，才能看到更远的地方。

#### 最近很喜一句话：“有道无术 术尚可求。有术无道，止于术。”

## 推荐阅读

- [【开源电商基础介绍】了解一个电商基础](https://mp.weixin.qq.com/s/d7TAOzcCtjpNwqqAeU8ftA)
- [【开源电商快速浏览】不会运行没关系，跟着文档找节奏](https://mp.weixin.qq.com/s/DrRn0Zx-WPMe_Ocg7Oo1MA)
- [【开源电商服务部署】域名+后台服务](https://mp.weixin.qq.com/s/s5CqqlcLrDsLY8NEU47_4w)
- [【开源电商宝塔】宝塔使用和站点创建](https://mp.weixin.qq.com/s/2TDLMvmZM1EXDnJ39kR6Qw)
- [【开源电商表单工具】减少表单重复开发，拖拉拽搞定](https://mp.weixin.qq.com/s/1an2WYS10rwtWzQobs34kQ)
- [【开源电商无限极分类设计】前同事留下的经典功能](https://mp.weixin.qq.com/s/e8TNaRpdX71C74O3BtBa7A)
- [【开源电商基本功能介绍】组合数据](https://mp.weixin.qq.com/s/naRUwGHY1bOn9UepeOErTg)
- [【开源电商快速部署服务】基于宝塔](https://mp.weixin.qq.com/s/VZ5zCuScA-zZzZCYxfxByA)
- [一个标准的Springboot —+ vue + uniapp 的商城怎么部署](https://mp.weixin.qq.com/s/eFTr3-3w_5vA5veCdyCzZw)

此配置也应用于我们的开源项目 点击阅读全文了解