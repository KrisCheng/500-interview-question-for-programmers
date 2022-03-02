## Hard Interview Questions

本页面用于记录一些我认为比较难或者不太好回答的面试题（非算法，一般都是质量还不错的题），如果你有好的答案，请不吝赐教。

* **设计一个延迟在10ms以内，QPS 在10000的服务，需要考虑哪些点，或者怎么设计（技术选型等）（得物）**
  * 这种题一般问简历上没有实际高并发经验的人（比如我 Orz），属于抛个方向看看你有没有做过这方面研究，属于答得好不加分，答不上减分的题。最好分值，说一些基本理解，表示至少你知道一些基本的东西
  * 缓存（多读少写场景）
  * 异步（系统解耦，消息队列）
  * 数据库（索引，分库分表，读写分离）
  * [high-concurrency-design.md](https://github.com/doocs/advanced-java/blob/main/docs/high-concurrency/high-concurrency-design.md)



* **订单限流系统是怎么实现的（小红书）**
  * 三个指标（服务ID，当前单量，最大单量）
  * 加锁和释放的实现
  * [常见限流方案设计与实现](https://zhuanlan.zhihu.com/p/72980217)
  * [Understanding Rate Limiting Algorithms](https://www.quinbay.com/blog/understanding-rate-limiting-algorithms)



* **设计一个服务，用于实时统计一个直播间的在线人数（技术选型，实现等）（Shopee）**
  * 



* **如果当前系统访问量（比如下单量）扩展10倍，有哪些方面需要考量（Shopee）**
  * 



* **消息中间件和Redis等缓存在当前系统中的使用实践（多）**
  * Cache Manager，提供load，override，evict等方法
  * 通过decorator使用，如某些耗时且常用的query，添加ttl



* **项目使用Mongo的优势和原因（多）**
  * 敏捷迭代，初期需求变化频繁，灵活表结构，文档型数据库方便集成不同属性（schema less）
  * embedded document 场景匹配（Json格式表示包含关系，一对多，如Order等Model）
  * 弱一致性，保证了高性能（对于Payment等场景还是需要使用支持事务的数据库）
  * 横向扩展能力
  * [Why Use MongoDB](https://www.mongodb.com/why-use-mongodb)
  * [41 | MongoDB应用场景及选型](https://time.geekbang.org/course/detail/100040001-193615)

* **缓存一致性如何解决（Shopee）**
  * 



* **建索引的策略（如 A,B,C三个字段，常用SQL 语句为 SELECT A,B,C where B=80 AND C > 200, SELECT A,B,C where A=50 AND B=80 AND C = 200，如何分别建立索引）（Shopee）**
  * 



* **有哪些常用的负载均衡算法和实现（Shopee）**
  * 
    
  
* **为什么要用双亲委派模型，有没有别的实现方式，或者说Java为什么要这么设计？（阿里）**
  * 
