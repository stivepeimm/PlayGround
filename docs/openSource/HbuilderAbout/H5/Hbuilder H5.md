Hi 我是 大粽子

###  移动端项目打包，使用Hbuild

###  移动端 支持H5和微信小程序 商业版本已经支持 APP IOS 和 Android平台 

1. 更多关于Uniapp的问题 [uniapp官网](https://uniapp.dcloud.io/)

2. [下载uniapp开发者工具  ----> Hbuilder X](https://www.dcloud.io/hbuilderx.html)

3. 打包微信小程序则需要下载 [微信开发者工具](https://developers.weixin.qq.com/miniprogram/dev/devtools/stable.html)

4. 微信开发者工具可根据自己的电脑系统下载 ![](https://gitee.com/stivepeim/img4mk/raw/master/20210405204501.png)



###  注意

~~~
最外层项目包中有一个 domain.json文件，需要根据自己实际情况修改此文件内容

不可有注释 且json格式正确
~~~

![](https://gitee.com/stivepeim/img4mk/raw/master/20210405204642.png)



###  Hbuilder X 打包 H5

1. 打开Hbuilder X 点击  `文件 `

![](https://gitee.com/stivepeim/img4mk/raw/master/20210405204712.png)

2. 本地测试点击  `运行`

![](https://gitee.com/stivepeim/img4mk/raw/master/20210405204736.png)

3. 线上打包点击  `发行`

![](https://gitee.com/stivepeim/img4mk/raw/master/20210405204803.png)

4. 打包的时候出现下图点 `击发` 行即可，不需要输入域名![](https://gitee.com/stivepeim/img4mk/raw/master/20210405204831.png)

5. 打包成功如下图![](https://gitee.com/stivepeim/img4mk/raw/master/20210405204901.png)



我的公号，最近每天发布的都是基于开源电商周边的开发和各种避坑指南，

如果不了解可以订阅 开源电商话题 或者查看历史

电商Java和WEBPC管理端

- [【开源电商基础介绍】了解一个电商基础](https://mp.weixin.qq.com/s/d7TAOzcCtjpNwqqAeU8ftA)
- [【开源电商快速浏览】不会运行没关系，跟着文档找节奏](https://mp.weixin.qq.com/s/DrRn0Zx-WPMe_Ocg7Oo1MA)
- [【开源电商服务部署】域名+后台服务](https://mp.weixin.qq.com/s/s5CqqlcLrDsLY8NEU47_4w)
- [【开源电商宝塔】宝塔使用和站点创建](https://mp.weixin.qq.com/s/2TDLMvmZM1EXDnJ39kR6Qw)
- [【开源电商表单工具】减少表单重复开发，拖拉拽搞定](https://mp.weixin.qq.com/s/1an2WYS10rwtWzQobs34kQ)
- [【开源电商无限极分类设计】前同事留下的经典功能](https://mp.weixin.qq.com/s/e8TNaRpdX71C74O3BtBa7A)
- [【开源电商基本功能介绍】组合数据](https://mp.weixin.qq.com/s/naRUwGHY1bOn9UepeOErTg)
- [【开源电商快速部署服务】基于宝塔](https://mp.weixin.qq.com/s/VZ5zCuScA-zZzZCYxfxByA)

####  明天我们聊聊微信小程序本地调试和上线。