Hello 我是大粽子

孩子静悄悄，必定在作妖。我这三天静悄悄，也是在憋大招。

提前预告下，最近和视频号的文档正在较劲，剩下的功能大家猜猜。暂时没有留言功能，可以私信回复，猜对的下次购买时提我大名10块钱的优惠我还是能做主的。（手动狗头）

### npm install 动不动卡住咋办？

最近有很多同学找到我问，为什么我根据你的文档一步步来操作，最后还是安装失败了？

这。。。让我咋办（心里也是心疼你啊）

![npm install fail](https://gitee.com/stivepeim/img4mk/raw/master/20210519222745.png)

### 他的原因

就像这位童鞋，都搭梯子了但是还是安装失败！这还真可能和npm本身没啥关系。确认他有梯子之后我就让他连接手机网络之后再 npm install 然后呢？奇迹出现了！哈哈哈

![搭梯子 + 手机wifi + npm install 成功](https://gitee.com/stivepeim/img4mk/raw/master/20210519223023.png)

### 坑坑坑

有时候还真不是npm网站本身问题，这个问题疫情期间我就出现过一次。之前在公司可以远程的机器，现在在家里访问不到。是直接访问不通的那种，并非网络不稳。**折腾过程中在手机上ping了下对应的机器IP竟然是通的**，疫情期间我远程办公时连接服务器都是通过手机wifi来连接的，虽然给移动打过投诉电话，但站在软件行业的角度上看，这个并不是一两天能解决的。因为中国移动的宽带正在起步，这就是为什么电信是大哥的原因啊。

截图中的朋友遇到的问题和我是不是一样，看文章的你虽然有时候是根据文档一步步走，但毕竟和环境有很大的关系。一一排除下总能找到突破点的。

### 没梯子咋办？

第一种 cnpm 直接安装cnpm 命令 再使用时直接cnpm 命令即可

~~~shell
npm install -g cnpm --registry=https://registry.npm.taobao.org
~~~

第二种使用代理

~~~shell
npm config set registry https://registry.npm.taobao.org
~~~

注意安装cnpm的仅仅inatsll的时候使用cnpm 其他命令还是使用npm 要不可能会出现奇怪的问题。

![感谢淘宝团队](https://gitee.com/stivepeim/img4mk/raw/master/20210519223602.png)

![npm主站](https://gitee.com/stivepeim/img4mk/raw/master/20210519224324.png)

### 总结

有梯子甚好

没梯子，找镜像

没梯子找镜像还安装失败的换网络。