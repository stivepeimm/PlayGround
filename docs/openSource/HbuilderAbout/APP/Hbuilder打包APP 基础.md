### App打包

Hi 我是 大粽子 （粉丝不上1w 这句话不去）

### 1，模块配置

打开项目点击`manifest.json`  

![](https://img.kancloud.cn/09/a6/09a6906968e38dc6c0c818ade58f18f0_1129x513.png)  

模块配置勾选 支付、登录、分享、 ViderPlayer和自己需要用的模块填写相关配置`Ctrl+s`保存  

APP自动生成图标选择一个1024x1024的图片传上去，生成一下就好了



### 2，权限配置  

安卓的已经配置好了，ios的必须开发者填写相关的描述信息，需要用那些就填写哪些，ios必须填写详细，不然上架容易被拒  

![](https://img.kancloud.cn/28/04/28046e9f5d867ec73b90cca44b5c556a_1278x557.png)  

安卓的权限中文说明地址：[http://www.kjson.com/files/androidmanifest](http://www.kjson.com/files/androidmanifest)  

### 3，模块配置

1.  定位选择高德地图，App端只支持高德地图，所以尽量选择高德地图，key在高德开发平台就可以申请到

2.  OAuth 授权登录  

​    一键登录是uni-app官方自带的，详情请看官方文档  

​    地址：[https://uniapp.dcloud.io/univerify](https://uniapp.dcloud.io/univerify)

3.  自定义第三方登录比如：微信登录  

​    请填写相关的配置就可以了

4.  **注意：**  

​    ios端如果包含了任何第三方登录，那必须也得把苹果登录也带上，不然苹果上架审核不通过



> 根据苹果审核指南要求，如果 app 使用第三方或社交登录服务 (例如，Facebook 登录、Google 登录、通过 Twitter 登录、通过 LinkedIn 登录、通过 Amazon 登录或微信登录) 来对其进行设置或验证这个 app 的用户主帐户，则该 app 必须同时提供“通过 Apple 登录”作为同等选项。详情参考：[App Store 审核指南 - 通过 Apple 登录](https://developer.apple.com/cn/app-store/review/guidelines/#sign-in-with-apple)



说明：[https://ask.dcloud.net.cn/article/36651](https://ask.dcloud.net.cn/article/36651)  

5\. 支付、分享填写相关的配置就可以了  

6\. 如果有视频，需要勾选VideoPlayer(视频播放)  

![](https://img.kancloud.cn/31/f3/31f32ef654d4005f1f0eeb2348cfeab7_257x53.png)



### 4，App常用其它设置  

![](https://img.kancloud.cn/5e/8c/5e8c1083866c0ca214c44d28d95a3136_708x163.png)  

为了方便测试选择了全部支持，测试的时候由于各种模拟器支持的不一样所以都勾选了，打包上线的时候选择第一个就可以，不然ios容易出现以下问题  

![](https://img.kancloud.cn/ef/4a/ef4a3e518d5555b5dc8d0f68067ffe47_200x345.png)