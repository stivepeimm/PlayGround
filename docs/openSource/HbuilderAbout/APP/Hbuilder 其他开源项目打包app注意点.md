Hi 我是 大粽子 （粉丝不上1w 这句话不去）

### App打包（使用Hbuilder进行App打包）

### 一、修改接口地址

1.打开uni-app下config/app.js修改接口地址，将下图两个地址修改成您的域名  

![](https://img.kancloud.cn/1f/f2/1ff256be4e729d4547dba9af753da670_2560x1048.png)

### 二、配置参数

#### 1.打开 uni-app 根目录下的 manifest.json 文件， 点击《基础配置》，重新获取 uni-app应用标识，获取之后填写 应用名称，应用描述，应用版本名称，应用版本号

![](https://img.kancloud.cn/68/78/68785db571023492c93c7c6ee834c7bf_2560x1048.png)



### 2.点击《App图标配置》，上传APP的图标文件，点击《自动生成所有图标并替换》



![](https://img.kancloud.cn/a1/39/a13990329b2bdbc9affc03a231338d87_2560x1048.png)



### 3.点击《App模块配置》



3-1. 选择《Geolocation》，在《高德定位》和《百度定位》中选择一个，填写appkey\_ios 和 appkey\_android  

3-2. 选择《LivePusher》  

3-3. 选择《Maps》，在《高德地图》和《百度地图》中选择一个，填写appkey\_ios 和 appkey\_android  

![](https://img.kancloud.cn/33/33/3333f35179869df2f189842e39d2fca3_2560x1048.png)  

3-4. 选择《OAuth(登录授权)》，选择《微信登录》，填写开放平台的 appid 和 appsecret 以及 Universal Links  

注：IOS必须同时要选择苹果登录  

![](https://img.kancloud.cn/76/4f/764f39a1dd769fda4bf0ca530327e06e_2560x1048.png)  

3-5. 选择《Payment(支付)》，选择对应的支付方式，微信支付请填写开放平台的 appid 和 Universal Links  

3-6. 勾选《Push(消息推送)》  

3-7. 勾选《Share(分享)》，选择微信分享，填写开放平台的 appid 和 Universal Links  

![](https://img.kancloud.cn/d3/28/d3288578fa089a5799ff8bebdb940a91_2560x1048.png)  

3-8. 勾选《VideoPalyer(视频播放)》  

![](https://img.kancloud.cn/39/41/3941bda07b6d2f877cb5fe7a635c0636_2560x1048.png)



### 4.点击《App权限配置》，android会自动添加权限，IOS需要配置如下权限



![](https://img.kancloud.cn/be/52/be5270470410720c10c70dd92ba92bd5_2560x1048.png)



### 5.点击《App常用其他配置》，勾选《支持CPU类型》下的armeabi-v7a



![](https://img.kancloud.cn/65/bf/65bf706043019aaa40cc48407033ccb5_2560x1048.png)



### 三、打包APP



### 1.选择发行，点击原生app-云打包



![](https://img.kancloud.cn/83/20/8320e7a27e8d0bb7cab4defca798577f_2560x1048.png)



### 2.选择android和ios，填写对应的信息



![](https://img.kancloud.cn/12/e9/12e901e819bb8431496a61061c7e1ee9_2560x1048.png)  

![](https://img.kancloud.cn/ba/07/ba0749206923043d4c938e1169d6d4f1_2560x1048.png)



### 3.点击左下方打包，等待进度条完成后点击确定，等待打包完成，下载APP包即可



![](https://img.kancloud.cn/b6/af/b6af5977a1c6b369a5b48fa8e3e0d433_2560x1048.png)  

![](https://img.kancloud.cn/13/df/13df3dde11740eaf0eaf6d23761e69fb_2560x1048.png)

