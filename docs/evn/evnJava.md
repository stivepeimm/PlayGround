JDK 开发环境配置 - 别笑，扫盲我是认真的

> 有血有肉 有糖有米 微信搜索 **西北大粽子** 一个85后程序员，干货分享，思想奇特。愿和你能碰撞出智慧的火花，并且能照亮他人。能在这个世界上能留下点什么，不辜负这个好年华。
>
> 关注微信公众号 回复 666 领取我不定时更新的学习资料【视频-电子书-文档】，无论是提升还是毕设都能找到你想要的学习资料 

##### **JDK下载**

之前jdk还有自己的Java网站，自从被Oracle收购之后就只能从Oracle网站目录下查找了，步骤如下

1. Oracle 官网Java 产品 https://www.oracle.com/cn/java/

2. ![image-20201209171456444](https://gitee.com/stivepeim/img4mk/raw/master/20201209171456.png)

3. ![image-20201209171719284](https://gitee.com/stivepeim/img4mk/raw/master/20201209171719.png)

4. ![image-20201209172005929](https://gitee.com/stivepeim/img4mk/raw/master/20201209172005.png)

   

   

##### **参见上图根据自己的对应的平台下载即可**

注意官网下载需要注册账户才可以，如果下载老版本https://www.oracle.com/java/technologies/javase-downloads.html

> 根据自己需求下载即可
>
> ![image-20201209172634870](https://gitee.com/stivepeim/img4mk/raw/master/20201209172634.png)

> **为了方便也可以直接网盘下载**
>
> 链接:https://pan.baidu.com/s/1UWELszRLTQneNFsBN8fu-g  密码:f8gq



##### JDK **安装 以windows为例**

下一步下一不跟QQ安装差不多 windows环境顶多修改安装目录

> ##### **Windows环境变量配置**
>
> ![image-20201209172913198](https://gitee.com/stivepeim/img4mk/raw/master/20201209172913.png)
>
> ![image-20201209172951169](https://gitee.com/stivepeim/img4mk/raw/master/20201209172951.png)
>
> ![image-20201209173443905](https://gitee.com/stivepeim/img4mk/raw/master/20201209173443.png)
>
> ![image-20201209173519723](https://gitee.com/stivepeim/img4mk/raw/master/20201209173519.png)
>
> ![image-20201209173547023](https://gitee.com/stivepeim/img4mk/raw/master/20201209173547.png)
>
> ![image-20201209173611149](https://gitee.com/stivepeim/img4mk/raw/master/20201209173611.png)
>
> ![image-20201209173638088](https://gitee.com/stivepeim/img4mk/raw/master/20201209173638.png)
>
> ![image-20201209173706447](https://gitee.com/stivepeim/img4mk/raw/master/20201209173706.png)
>
> ![image-20201209173731294](https://gitee.com/stivepeim/img4mk/raw/master/20201209173731.png)

##### **不重启的情况下刷新环境变量**

在不重启电脑的情况下使刚设置的环境变量生效的方法：

以修改环境变量“PATH”为例，修改完成后，进入DOS命令提示符，输入：set PATH=C: ，关闭DOS窗口。再次打开DOS窗口，输入：echo %PATH% ，可以发现“我的电脑”->“属性”->“高级”->“环境变量”中设置的 PATH 值已经生效。

不用担心DOS窗口中的修改会影响环境变量的值，DOS窗口中的环境变量只是Windows环境变量的一个副本而已。但是对副本的修改却会引发Windows环境变量的刷新，这正是我们想要的！



> 有血有肉 有糖有米 微信搜索 **西北大粽子** 一个85后程序员，干货分享，思想奇特。愿和你能碰撞出智慧的火花，并且能照亮他人。能在这个世界上能留下点什么，不辜负这个好年华。
>
> 关注微信公众号 回复 666 领取我不定时更新的学习资料【视频-电子书-文档】，无论是提升还是毕设都能找到你想要的学习资料 