## System Design

System Design 已经成了面试标配了，这个问题有很多种问法，比如外企会有专门的System Design 面，从API，到技术选型，到DB，到表结构，国内有些公司也会面，但大多没那么严谨，但这已经越来越成为面试必备的一些资源了，所以作为单独页面拆分开来准备。



* **设计一个延迟在10ms以内，QPS 在10000的服务，需要考虑哪些点，或者怎么设计（技术选型等）（得物）**
  * 这种题一般问简历上没有实际高并发经验的人（比如我 Orz），属于抛个方向看看你有没有做过这方面研究，属于答得好不加分，答不上减分的题。最好分治，说一些基本的理解，表示至少你知道一些基本的东西
  * 缓存（多读少写场景）
  * 异步（系统解耦，消息队列）
  * 数据库（索引，分库分表，读写分离）
  * [high-concurrency-design.md](https://github.com/doocs/advanced-java/blob/main/docs/high-concurrency/high-concurrency-design.md)



* **设计一个服务，用于实时统计一个直播间的在线人数（技术选型，实现等）（Shopee）**
  * 
    
* **设计一个点赞系统（字节跳动）**
  * [Design a system that tracks the number of “likes”](https://medium.com/@morefree7/design-a-system-that-tracks-the-number-of-likes-ea69fdb41cf2)



* **如果当前系统访问量（比如下单量）扩展10倍，有哪些方面需要考量（Shopee）**
  * 



* **设计一个Event Driven Framework（Nvidia）**

  * 有多个微服务构成一个pipeline，下一个执行微服务依赖于之前的中间的生成数据，设计一个类似这样的Event Driven Framework（可包括DB, API等）
  * 

  

  

* **如何设计一个秒杀系统（小红书）**

  * 应付答案见 [Java开发面试：高并发秒杀系统如何设计与优化](https://blog.csdn.net/CSDN_Terence/article/details/77744042) / [如何设计一个秒杀系统](https://blog.csdn.net/suifeng3051/article/details/52607544)
  * 进阶执行方案见 [如何设计一个百万级用户的抽奖系统](https://note.youdao.com/ynoteshare1/index.html?id=5c04dccbffd0b6fc511dc920e6be12e3&type=note) （携程大佬）
  * 详细实战经验见 [秒杀系统设计与实现.互联网工程师进阶与分析](https://github.com/qiurunze123/miaosha)
  * 面试装逼可看 [如何设计一个秒杀系统](https://time.geekbang.org/column/article/40153) 



* **高并发访问下如何保证用户名不冲突，比如多个用户同时创建同一个用户名（拼多多）** 



* **权限管理是如何设计的(星环)**  
