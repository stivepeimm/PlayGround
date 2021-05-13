

### 布隆过滤器是什么

名字就跟每个定律一样，你问为什么叫牛顿定律，因为是牛顿发明或者发现的。「瞪眼」

他能做什么？它是将一个二进制向量和函数映射，布隆过滤器可以用在检测元素是否存在某个集合或者用于快速检索中。

> 缺点: 有一定的删除问题和错误识别率
>
> 优点：查询时间和空间都远远超过普通算法

### 布隆过滤器Bloom Filter 是怎么实现的

添加Item或者元素时，创建一个散列函数和一个KEY形成映射，设置的数据=1，只要检索时判断 =1就知道这个数据存不存在，有了此方法，查询时发现有0的则证明一定不存在，那么反过来讲如果是1证明元素很可能存在，

注意这里为什么说很可能存在，因为他有一定的识别错误，但这个错误在实际生产过程中可以忽略，毕竟利大于弊么。

看文字晕晕乎乎，不动就画图，来看看应该就会明白许多。

![布隆过滤器](https://gitee.com/stivepeim/img4mk/raw/master/20210413103552.png)

![全局鸟瞰图](https://gitee.com/stivepeim/img4mk/raw/master/20210414180509.png)

### 说人话

布隆过滤器到底能干啥？

特殊的id暂且不提哈，数据库id基本都是自增的对吧！我们传递id后端去DB查询，这个非常合理。

但是如果我们用负数查询呢？一两条无所谓，如果成千上万呢？基本上数据库都会很大压力扛不住，服务器配置暂且不说，拖慢系统运行速度甚至宕机都是有可能的，这样是不是布隆过滤器的有点有展现的淋漓尽致。【狗头】

这么吊，也是有代价的，因为它也拿不准，存在一定程度的判断失误！

问：为什么会误判？

答：搜索的key没在容器中，但是hash后得到的key都是1 。假如布隆过滤器中有黑名单，那么直接创建一个白名单就搞定了。

问：为什么不容易删除？

答：我们提到正确的数据Key值=1，但不能因为=0就删掉他，这可能会影响其他元素的判断 不过可以了解下Counting Bloom Filter 「下一篇文章」

### 说了这么多咋实现

> 1：预估数量n以及期望的误判率FPP
>
> 2:  hash函数和bit集合的size大小

### Bit集合Size大小

![](https://gitee.com/stivepeim/img4mk/raw/master/20210413142626.png)

### 函数 哈希选择，预估值n和bit数组长度m获取hash函数Key

![](https://gitee.com/stivepeim/img4mk/raw/master/20210413143024.png)

### 怎么用？maven项目中添加

~~~ xml
 <dependency>
            <groupId>com.google.guava</groupId>
            <artifactId>guava</artifactId>
            <version>23.0</version>
 </dependency>    



~~~

一段我写的测试代码

~~~ java
/**
 * 布隆过滤器 - 用于redis缓存穿透 的情况
 * @author 作者 西北大粽子
 */
public class TestBloomFilterByDZZ {

    private static int total = 19999;
    private static BloomFilter<Integer> bfilter = BloomFilter.create(Funnels.integerFunnel(), total);

  // 初始化数据
    public static void main(String[] args) {
        for (int i = 0; i < total; i++) {
            bfilter.put(i);
        }

        // 是否有匹配不上的
        for (int i = 0; i < total; i++) {
            if (!bfilter.mightContain(i)) {
                System.out.println("有没关注西北大粽子的 溜了。。。");
            }
        }

        // 不再内的有多少匹配出来
        int count = 0;
        for (int i = total; i < total + 10000; i++) {
            if (bfilter.mightContain(i)) {
                count++;
            }
        }
        System.out.println("炮灰陪跑：" + count);
    }

}
~~~

### 可适用的业务场景

1：当一个入库数据量比较大的时候，可以用作名称或者唯一件做检查，存在则跳过不存在则入库

2：过滤垃圾邮件，这是一段计算你可以结合自己的业务了解下。

![](https://gitee.com/stivepeim/img4mk/raw/master/20210413145000.png)



### 日常求关注，素质一键三连。

### 每周至少3篇原创文章，在被业务折磨的情况下还能留下点什么。

### 最近很喜欢的一句话 “有道无术，术尚可求。有术无道，止于术。”

![求关注](https://gitee.com/stivepeim/img4mk/raw/master/20210413150115.png)