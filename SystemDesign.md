## System Design

System Design 已经逐渐成了面试标配了，这个问题有很多种问法，比如外企会有专门的System Design 面，从架构，技术选型。API，到DB，表结构 等持续1小时左右的面试，当前阶段国内有些公司也会面，但大多没那么严谨，可能就几分钟。不过这已经越来越成为面试必备项了，所以作为单独页面拆分开来准备也是有必要的（BTW，这不比考八股好玩？）。



* **[Design a Event Driven Framework](system_design/EventDrivenFramework.md)**
* **[Design a Logging System](system_design/LoggingSystem.md)**
* **[Design a Rate Limiter](system_design/RateLimiter)**
* **[Design a Weibo](system_design/Weibo)**



* **设计一个延迟在10ms以内，QPS 在10000的服务，需要考虑哪些点，或者怎么设计（技术选型等）（得物）**
  * 这种题一般问简历上没有实际高并发经验的人（比如我 Orz），属于抛个方向看看你有没有做过这方面研究，属于答得好不加分，答不上减分的题。最好分治，说一些基本的理解，表示至少你知道一些基本的东西
  * 缓存（多读少写场景）
  * 异步（系统解耦，消息队列）
  * 数据库（索引，分库分表，读写分离）
  * [high-concurrency-design.md](https://github.com/doocs/advanced-java/blob/main/docs/high-concurrency/high-concurrency-design.md)



* **设计一个服务，用于实时统计一个直播间的在线人数（技术选型，实现等）（Shopee）**



* **设计一个点赞系统（字节跳动）**
  * 这个题当时拿到就开始讲，其实这种做法是不对的，点赞千千万，有对朋友圈的点赞，有对文章的点赞，视频的点赞，需要先问清楚点赞的对象（DB设计的基础）
  * 是否需要查看点赞的具体人数，点赞是否能取消（这可以决定你的存储如何设计，如：如果不需要记录由谁点赞，可以做成批处理，减少对DB的访问，pre-aggregate）
  * 强调使用  Eventually Consistence（缓存，batch update）
  * 如果需要看点赞详情，可以取消赞（如：朋友圈点赞）
    * [如何使用Redis设计个简单的点赞系统？](https://aijishu.com/a/1060000000059449)
  * 如果只需要统计数目，不能取消赞（如：直播场景等）
    * batch processing，比如每分钟的count（直播等短时场景） || 点赞细则 + 一张额外的counter表（batch update）
    * [Design a system that tracks the number of “likes”](https://medium.com/@morefree7/design-a-system-that-tracks-the-number-of-likes-ea69fdb41cf2)



* **如果当前系统访问量（比如下单量）扩展10倍，有哪些方面需要考量（Shopee）**



* **如何设计一个秒杀系统（小红书）**

  * 应付答案见 [Java开发面试：高并发秒杀系统如何设计与优化](https://blog.csdn.net/CSDN_Terence/article/details/77744042) / [如何设计一个秒杀系统](https://blog.csdn.net/suifeng3051/article/details/52607544)
  * 进阶执行方案见 [如何设计一个百万级用户的抽奖系统](https://note.youdao.com/ynoteshare1/index.html?id=5c04dccbffd0b6fc511dc920e6be12e3&type=note) （携程大佬）
  * 详细实战经验见 [秒杀系统设计与实现.互联网工程师进阶与分析](https://github.com/qiurunze123/miaosha)
  * 面试装逼可看 [如何设计一个秒杀系统](https://time.geekbang.org/column/article/40153) 



* **权限管理是如何设计的（项目相关，也可以作为一个单独的System Design 题）(星环)**  



* **一个前端页面，需要加载一个大的数据集（横坐标为时间，纵坐标为数据），还需要支持缩放，点击查看元数据等功能，可从前后端角度讲讲怎么设计和优化（开放题）（Nvidia）**



* **设计一个ATM系统（微软）**
  * 需求：设计一个ATM系统，包括存/取款，跨行转账等功能
  * ATM
    * [ATMInfo, State]
    * autherUser()
  * User
    * [UserInfo, availableBalance, totalBalance] (金额信息也可以单独成 Account对象，或者方法调用) 
    * makeTransaction() --> 统一的事务操作对象（查询 / 存入 / 提现 / 转账）
    * 注：此处可以讨巧，问一个用户是否应该只有一张卡，如果是，设计可以省一些事情
  * Card
    * [No, CardInfo, pin]
  * Transation (由BankService 调用 ，不同Bank具体实现)
    * 所有操作（查询 / 存入 / 提现 / 转账）均继承自Transaction (Type / Status)
  * [ATM — An Object-Oriented Design](https://medium.com/swlh/atm-an-object-oriented-design-e3a2435a0830) （OOP设计思路）
  * [Design an ATM](https://github.com/tssovi/grokking-the-object-oriented-design-interview/blob/master/object-oriented-design-case-studies/design-an-atm.md)
  * [ATM LOW LEVEL DESIGN ](https://www.youtube.com/watch?v=_ppHN3SeFnw) （YouTube low level design of OOP）
  * [Database design: Calculating the Account Balance](https://stackoverflow.com/questions/4373968/database-design-calculating-the-account-balance)
  



* **设计一个生产者-消费者模型（Nvidia）**
  * 需求：
    1. 每个时钟生产者会产生记录，形式为数据区间，如[0,2]（为了简单，可认为各个数据区间没有交集）；
    2. 每个时钟消费者也会消费数据，可能是[0,5]，如果和生产者的区间有交集，比如[3,6]，这条记录计算消费掉；
    3. 输出未被消费的数据



* **设计一个物流系统**



* **Design a ID generator**
  * System Design Interview – An Insider's Guide [Download](https://hubpdf.com/e-books/computers/system-design-interview-pdf-book-free-download/) Chapter 7
  * [Ace the System Design Interview — Distributed ID Generator](https://towardsdatascience.com/ace-the-system-design-interview-distributed-id-generator-c65c6b568027)
  * [Design Unique ID Generator](https://docs.google.com/presentation/d/1Eb1L-eyVdbLaywfi6MCqsdvwXZCRGhVREFrUcvM-azg/edit#slide=id.p)



* **Design a key-value storage**
  * System Design Interview – An Insider's Guide [Download](https://hubpdf.com/e-books/computers/system-design-interview-pdf-book-free-download/) Chapter 6
  * [Mock1](https://docs.google.com/document/d/1vKQyUat_C3RP55LskPHfYRxhYZn5Y5I2szXX-4ixi6U/edit) / [Mock2](https://docs.google.com/document/d/1pqsaPts9fLFt2x3YFmG6D0KK-u3-wPIP6Nq4JAinGhY/edit)



* **Design a Tiny URL**
  * [系统设计(五) Design Tiny URL System](https://docs.google.com/presentation/d/1v5QA1h-kPQ3EXdxMbyKGkYhlkaf8otqf9TubnY00vQo/edit#slide=id.ge7b631cedb_0_0)
  * System Design Interview – An Insider's Guide [Download](https://hubpdf.com/e-books/computers/system-design-interview-pdf-book-free-download/) Chapter 8
