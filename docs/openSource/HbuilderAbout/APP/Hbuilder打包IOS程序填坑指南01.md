Hi 我是 大粽子 （粉丝不上1w 这句话不去）

### 前景介绍

Uniapp 开发的小程序打包APP

Uniapp 一个类似vue开发的套路可以通过差异化配置实现各种平台小程序，H5 当然不是写依据代码导出运行，也会有差异化提示

至于Uniapp是什么后面会出文章针对介绍，这个先挂账上。【狗头】

### 适配APP【IOS和Android】

Android的开放度基本跟随一个帖子就搞定，但IOS就能折腾死人。

Apple开发者账户申请，这个必须得有。重要截图如下

![](https://gitee.com/stivepeim/img4mk/raw/master/20210323200622.png)

官方的指引文档，其实还是可以的，但就因为说明和截图不是现在最新的mac OX，如果是ios开发还好，不经常搞ios证书直接看有点乱！https://ask.dcloud.net.cn/article/152

### IOS证书申请步骤

1. 创建证书
2. 创建证书前需要根据uniapp的文档和信息用钥匙串请求一个CertificateSigningRequest.certSigningRequest 的文件
3. ![](https://gitee.com/stivepeim/img4mk/raw/master/20210323200802.png)
4. ![](https://gitee.com/stivepeim/img4mk/raw/master/20210323200824.png)
5. ![](https://gitee.com/stivepeim/img4mk/raw/master/20210323200901.png)
6. ![](https://gitee.com/stivepeim/img4mk/raw/master/20210323200928.png)
7. ![](https://gitee.com/stivepeim/img4mk/raw/master/20210323201004.png)
8. ![](https://gitee.com/stivepeim/img4mk/raw/master/20210323201040.png)
9. ![](https://gitee.com/stivepeim/img4mk/raw/master/20210323201111.png)

明天再讲P12证书的问题，下班狗命要紧

![](https://gitee.com/stivepeim/img4mk/raw/master/20210306212709.png)

![](https://gitee.com/stivepeim/img4mk/raw/master/20201226230441.gif)