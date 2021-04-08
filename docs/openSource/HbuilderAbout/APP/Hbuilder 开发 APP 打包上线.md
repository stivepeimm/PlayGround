Hi 我是 大粽子 （粉丝不上1w 这句话不去）

### App打包上线

一、安卓端  

1，点击发行>原生-app云打包  

![](https://img.kancloud.cn/14/78/147853f6716b3351dc1e4ebf5266c823_670x823.png)  

正式包和自定义调试基座的区别看这篇文章  

[https://ask.dcloud.net.cn/article/35115](https://ask.dcloud.net.cn/article/35115)  

2，生成证书  

教程：[https://ask.dcloud.net.cn/article/35777](https://ask.dcloud.net.cn/article/35777)  

3.**签名生成工具**  

用于获取安装到手机的第三方应用签名的apk包。点击下载 \[签名生成工具\]  

下载链接：([https://res.wx.qq.com/open/zh\_CN/htmledition/res/dev/download/sdk/Gen\_Signature\_Android2.apk](https://res.wx.qq.com/open/zh_CN/htmledition/res/dev/download/sdk/Gen_Signature_Android2.apk))  

配置好以后点击打包，打包成功后控制有链接自行下载就可以了  

4，在自己需要的平台选择性上架APP



二、苹果端（必须在macOs系统中操作以下流程）  

1，申请苹果开发者账号，进入网址注册或者登陆  

[https://developer.apple.com/](https://developer.apple.com/)  

![](https://img.kancloud.cn/26/b6/26b651e4757306e367f6d3e26ec1646f_1436x766.png)  

2，在手机Appstore里面搜索 Developer 下载，打开软件点击我的-现在注册，按照格式注册开发者账号  

![](https://img.kancloud.cn/55/51/555129ee562dbcc2e44d8eb73496ba48_750x1334.png)  

3，注册好以后登陆苹果开发者网站  

[https://developer.apple.com/](https://developer.apple.com/)  

4，生成苹果证书教程和p12文件  

教程：[https://www.jianshu.com/p/ae11b893284b](https://www.jianshu.com/p/ae11b893284b)  

5，打包App  

微信所有的相关配置需要appid和需要生成ios平台通用链接  

ios通用链接配置  

[https://ask.dcloud.net.cn/article/36393#unilink](https://ask.dcloud.net.cn/article/36393#unilink)  

ios通用链接生成  

教程：[https://ask.dcloud.net.cn/article/36445](https://ask.dcloud.net.cn/article/36445)  

填写好所有配置后  

发行-原生App云打包-勾选ios包  

![](https://img.kancloud.cn/42/7a/427a74c0ebf860cc2b62db8ae06b6d3b_666x826.png)  

生成好ipa文件后，在Transporter这个软件上传  

![](https://img.kancloud.cn/d6/77/d677fdb0ec81072f2f82c523591b6891_276x300.png)



6，上传测试版本 登陆开发者中心点击  

![](https://img.kancloud.cn/a5/50/a550a2c872103f98c14e9c0164571543_1110x273.png)  

选择我的App  

![](https://img.kancloud.cn/cd/1b/cd1bc1ef9ae707a20c7209e4907e1654_1511x630.png)  

![](https://img.kancloud.cn/d9/4e/d94ee40f1fa2fa62921d5b31092abdbb_2019x710.png)  

在TestFlight这个里面可以看到上传的版本，点击进去后可以添加测试人员还有一些别的操作



7，查看测试版本  

手机端下载TestFlight软件登录进去，点击兑换，填写邀请码，邀请码是通过添加测试人员的时候发的邮件就有  

8，下载测试  

9，上架Appstore  

在Apple开发者平台点击AppStore，填写里面所有的相关配置再点击右上角的提交就上架审核了，审核通过后在手机Appstore就可以搜到上架的应用  

![](https://img.kancloud.cn/2d/9a/2d9a99ef89c8fb8c15d3117f210dc8eb_1748x931.png)  

**注意**： **上架的时候最好把推广分享功能暂时先关闭了，等各个平台审核通过后在打开 经验啊**