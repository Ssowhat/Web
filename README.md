# 前言

​	近几年，人工智能无疑成为人们口中的热点话题。先是Google的AlphaGo，后有百度的度秘、无人车，微软必应搜索推出的小冰也是新闻不断。这一系列人工智能产品的推陈出新，令人眼花缭乱，一时间给人的感觉是人工智能遍地开花。无论人们接受还是不接受，人工智能都在迅速渗透各行各业。安全作为一个传统行业，基于规则以及黑白名单的检测技术已经发展到了一定的瓶颈，而利益驱动的黑产团伙，其技术的发展已经远远超乎我们的想象。如何借助人工智能的力量，提升安全行业的整体检测与防护能力，成为各大安全厂商研究的课题。国内安全行业，随着BAT3以及大量新兴的创业企业进入企业安全领域，他们凭借着自身数据搜集、处理、积累以及人工智能方面优势，正在逐渐改变着整个安全行业，安全产品的形态从硬件盒子逐步走向混合模式以及云端SaaS服务，安全技术从重防御逐步走向数据以及智能驱动。传统安全企业也凭借其强大的安全人才储备，迅速推进人工智能在安全产品的落地。

​	我在安全这个行业搬了好几年砖，前五年做大型互联网公司的企业安全建设，从准入系统到WAF、SIEM、IPS等，基本都开发或者使用过，最近三年一直负责云安全产品，从抗D、WAF产品到、SIEM、入侵检测等，使用的技术从规则、黑白名单、模型、沙箱再到机器学习，从单机的OSSIM到Hadoop、Storm、Spark、ELK，也算目睹了安全技术或者更准确的说数据分析处理技术的迅猛发展。我深深感到使用人工智能技术改变这个行业，不是我们的选择，而是必经之路。我真正意义上接触机器学习是2014年底，当时带领了一个很小的团队尝试使用机器学习算法解决安全问题，磕磕碰碰一直走到现在，变成几十人的一个产品团队。本书是我机器学习三部曲的第一部，主要以机器学习常见算法为主线，以生活中的例子和具体安全场景介绍机器学习常见算法，定位为机器学习入门书籍，便于大家可以快速上手。全部代码都在普通PC电脑上可以运行。第二部将重点介绍深度学习，并以具体的十个案例介绍机器学习的应用，定位是面向具有一定机器学习基础或者致力于使用机器学习解决工作中问题的读者，全书的重点集中在问题的解决而不是算法的介绍。由于深度学习通常计算量已经超过了PC的能力，部分代码需要在服务器甚至GPU上运行，不过这不影响大家的阅读与学习。第三部将重点介绍强化学习和对抗网络，并以若干虚构安全产品或者项目介绍如何让机器真正具备AlphaGo级别的智能。

​	本书的第1章概括介绍了机器学习的发展以及互联网目前的安全形势。第2章介绍了如何打造自己的机器学习工具箱。第3章概括介绍了机器学习的基本概念。第4章介绍web安全的基础知识。第5章到第13章介绍浅层机器学习算法，包括常见的K近邻、决策树、朴素贝叶斯、逻辑回归、支持向量机、K均值、FP-growth与Apriori、隐式马尔可夫、有向图。第14章到第17章介绍神经网络以及深度学习中常用的递归神经网络和卷积神经网络。每章都会以生活中的例子开头，让读者有一个感性的认识，然后是简短的基础知识的介绍，最后是以安全领域的2-3个例子，讲解如何使用该算法解决问题，全书定位是能让更多的安全爱好者以及信息安全从业者可以了解机器学习，动手使用简单的机器学习算法解决实际问题，所以全书尽量避免生硬的说教，能用文字描述的尽量不用冷冰冰的公式，能用图和代码说明的尽量不用多余的文字，正如霍金说言，”多写1个公式，少一半读者”，希望反之亦然。具体到机器学习应用于安全领域，遇到的最大问题就是缺乏大量的黑样本，即所谓的攻击样本，尤其相对于大量的正常业务访问，攻击行为尤其是成功的攻击行为是非常少的，这就给机器学习带来了很大挑战。本书中很少对不同算法进行横向比较，也是因为确实不同场景下不同算法表现差别很大，很难说深度学习就一定比朴素贝叶斯好，也很难说支持向量机就比不过卷积神经网络，拿某个具体场景进行横评意义不大，毕竟选择算法不像购买SUV，可以拿几十个参数评头论足，最后还是需要大家结合实际问题去选择。

​	这里我要感谢我的家人对我的支持，本来工作就很忙，没有太多时间处理家务，写书以后更是花费了我大量的休息时间，我的妻子无条件承担起了全部家务尤其是照料孩子方面的繁杂事务。我很感谢我的女儿，写书这段时间几乎没有时间陪她玩，她也很懂事的自己玩，我也想用这本书作为她的生日礼物。我还要感谢编辑吴怡对我的支持和鼓励，让我可以坚持把这本书写完。最后还要感谢各位业内好友尤其是我boss对我的支持，排名不分先后：马杰@百度安全、冯景辉@百度安全、林晓东@百度基础架构、黄颖@百度IT、李振宇@百度AI、Lenx@百度安全、黄正@百度安全、程岩@百度云、郝轶@百度云、云鹏@百度无人车、赵林林@微步在线、张宇平@数盟、谢忱@Freebuf、李新@Freebuf、李琦@清华、徐恪@清华、王宇@蚂蚁金服、王泯然@蚂蚁金服、王龙@蚂蚁金服、周涛@启明星辰、姚志武@借贷宝、刘静@安天、刘元军@医渡云、廖威@易宝支付、[尹毅](https://item.jd.com/10082081248.html)@sobug、宋文宽@联想、团长@宜人贷、齐鲁@搜狐安全、吴圣@58安全、康宇@新浪安全、幻泉@i春秋、雅驰@i春秋、王庆双@i春秋、张亚同@i春秋王禾@微软、李臻@paloalto、西瓜@四叶草、郑伟@四叶草、朱利军@四叶草、土夫子@XSRC、英雄马@乐视云、sbilly@360、侯曼@360、高磊@滴滴、高磊@爱加密、高渐离@华为、刘洪善@华为云、宋柏林@一亩田、张昊@一亩田、张开@安恒、李硕@智联、阿杜@优信拍、李斌@房多多、李程@搜狗、Tony@京东安全、简单@京东安全、姚聪@face+、李鸣雷@金山云，最后我还要感谢我的亲密战友陈燕、康亮亮、蔡奇、哲超、新宇、子奇、月升、王磊、碳基体、刘璇、钱华沟、刘超、王胄、吴梅、冯侦探、冯永校。

​	本书面向信息安全从业人员、大专院校计算机相关专业学生以及信息安全爱好者，机器学习爱好者，对于想了解人工智能的CTO、运维总监、架构师同样也是一本不错的科普书籍。如果看完本书，可以让读者在工作学习中遇到问题可以想起一到两种算法，那么我觉得就达到效果了，如果可以让读者可以像使用printf一样使用SVM、朴素贝叶斯等算法，那么这本书就相当成功了。

​	我平时在Freebuf专栏以及i春秋分享企业安全建设以及人工智能相关经验与最新话题，同时也运营我的微信公众号”兜哥带你学安全”，欢迎大家关注并在线交流。

​	本书使用的代码和数据均在github上发布，对应地址为：

[https://github.com/duoergun0729/1book](https://github.com/duoergun0729/1book)

​	代码层面任何疑问可以在github上直接反馈。

​	我的公众号二维码为：

![img](https://github.com/duoergun0729/4book/raw/master/photo/logo/qrcode_for_gh_810edc392056_258.jpg)

​       我的i春秋专栏二维码为：

![img](https://github.com/duoergun0729/4book/raw/master/photo/logo/i%E6%98%A5%E7%A7%8B.png)

 