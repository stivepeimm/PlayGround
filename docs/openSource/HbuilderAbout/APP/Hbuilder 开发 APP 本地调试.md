Hi 我是 大粽子 （粉丝不上1w 这句话不去）

### App开发调试

一、Windows端  

1，安装java 选择 Windows x64  

下载地址：[https://www.oracle.com/java/technologies/javase/javase-jdk8-downloads.html](https://www.oracle.com/java/technologies/javase/javase-jdk8-downloads.html)  

2，安装Android Studio （此软件需要翻墙），可以用这个中文网  

下载地址：[http://www.android-studio.org/](http://www.android-studio.org/)  

用andriod自己的开发调试工具会出现代码热更新失败，安卓adb冲突，所以推荐第三方模拟器  

安装雷电模拟器或者mumu模拟器 我这里选择选择的是mumu模拟器  

安装好后在设置中心>高级设置选择  

![](https://img.kancloud.cn/e5/dd/e5dd2f517082f0bb9a7a2c8e9ad2493a_666x639.png)  

打开Hbuildx 编辑器设置Android模拟器端口配置和ADB路径  

双击App.vue文件>点击运行>运行到手机或模拟器>Android模拟器端口配置



![](https://img.kancloud.cn/32/67/32676b13caa90c4fd9cb86615ba28866_1552x615.png)  

mumu模拟器的默认端口是7555，别的模拟器端口需要去官方网站上面去查询，adb路径就是模拟器安装的路径，修改好后保存  

![](https://img.kancloud.cn/54/6a/546af04450dcd567317d7adc7441814e_1705x742.png)  

然后启动模拟器，重启HbuildX软件，等待一会点击运行>运行带手机或者模拟器 这时候就能看到模拟器的设备了，看不到的话需要关闭HbuildX，先开模拟器再打开HbuoldX编辑器  

![](https://img.kancloud.cn/80/d7/80d7a1b54804fd70064c3e0cc24addff_1593x614.png)  

然后点击运行就可以调试了  

二、mac端安装xCode，安装苹果模拟器，在ios模拟器里面选择手机样式  

![](https://img.kancloud.cn/3c/bd/3cbd2740f409b6015aa0d54da93cff3d_1620x638.png)  

三、真机调试  

1，安卓连接数据线之后开启开发者模式，不打开开发者识别不到安卓手机  

2，苹果手机下载iTunes 官方说下载低版本的  

![](https://img.kancloud.cn/ca/23/ca237cc3c1e018416925f620be424aaf_909x399.png)  

下载地址：[https://mydown.yesky.com/pcsoft/33491427/versions/](https://mydown.yesky.com/pcsoft/33491427/versions/)  

然后点击运行-运行带手机或者模拟器就可以看到设备了，点击运行就行了  

![](https://img.kancloud.cn/f8/dc/f8dc3b11df4e1862f464e10794d7c929_1974x620.png)  

四、各种问题解决方案  

[https://ask.dcloud.net.cn/article/151](https://ask.dcloud.net.cn/article/151)  

[https://ask.dcloud.net.cn/article/97](https://ask.dcloud.net.cn/article/97)  

[https://ask.dcloud.net.cn/article/36195](https://ask.dcloud.net.cn/article/36195)