## Not Bagu

本页面用于记录一些我认为比较难或者不太好回答的面试题（非算法/系统设计，一般都是质量还不错的题，有些基于项目来问），如果你有更好的答案，请不吝赐教。



* **订单限流是怎么实现的（多），分布式场景下的限流又如何实现（字节跳动）**
  * 基于redis [setnx](https://redis.io/commands/setnx) 命令实现分布式锁（时间区间段的while循环中获取，拿到直接返回，key为服务ID，value为uuid随机生成，[expire](https://redis.io/commands/expire) 指令设置超时时间），拿到锁后进行当前单量判断和更新redis操作（hget，hset），超过max则向上抛出异常（setnx + expire的实现，问题在于这两步非原子操作）
  * 三个指标（物流服务ID为key，当前单量，最大单量）
  * 最大单量的更新为一个cronjob，更新redis
  * [如何设计一个分布式限流器（distributed rate limiter）](https://guanhonly.github.io/2020/05/30/distributed-rate-limiter/)（概念扫盲篇）
  * [Understanding Rate Limiting Algorithms](https://www.quinbay.com/blog/understanding-rate-limiting-algorithms) （概念扫盲篇，EN）
  * [限流算法基本代码实现](https://juejin.cn/post/6870396751178629127)
  * [分布式锁的实现之 redis 篇](https://xiaomi-info.github.io/2019/12/17/redis-distributed-lock/)
  * [Distributed locks with Redis](https://redis.io/topics/distlock)
  



* **对分布式事务的理解（字节跳动）**
  * 两阶段提交
    * 准备（投票）阶段：”对于数据库来说，准备操作是在重做日志中记录全部事务提交操作所要做的内容，它与本地事务中真正提交的区别只是暂不写入最后一条 Commit Record 而已“
    * 提交阶段：”阶段的提交操作应是很轻量的，仅仅是持久化一条 Commit Record 而已“
  * 三阶段提交
    * CanCommit
    * PreCommit
    * DoCommit
  * TCC事务（"Try-Confirm-Cancel"）
    * Try：尝试执行阶段，完成所有业务可执行性的检查（保障一致性），并且预留好全部需用到的业务资源（保障隔离性）
    * Confirm：确认执行阶段，不进行任何业务检查，直接使用 Try 阶段准备的资源来完成业务处理。Confirm 阶段可能会重复执行，因此本阶段所执行的操作需要具备幂等性
    * Cancel：取消执行阶段，释放 Try 阶段预留的业务资源。Cancel 阶段可能会重复执行，也需要满足幂等性
  * [《凤凰架构》第3章 事务处理](http://icyfenix.cn/architect-perspective/general-architecture/transaction/)



* **物流商鉴权是怎么做的（比如如何判断某些单只能某物流商下）（多）**
  * api key
    
* **接口幂等如何实现**
  * 基于transaction_id判断



* **消息中间件和Redis等缓存在当前系统中的使用实践（多）**
  * MQ（kafka）用于订单创建和三方物流商通信两个模块，为异步过程
  * 基于redis 实现CacheManager，提供load，override，evict等方法
  * 某些耗时或常用query（物流商列表，渠道列表等），添加ttl，保证读取效率，减少数据库访问
  * redis用于分布式锁（订单限流等场景）
  * reidis pub/sub机制（某些数据（如ENUM）需常驻内存，更新时避免机器反复重启）[参考](https://redis.com/redis-best-practices/communication-patterns/pub-sub/)



* **项目使用Mongo的原因和优势（多）**
  * 敏捷迭代，初期需求变化频繁，灵活表结构，文档型数据库方便集成不同属性（schema less）
  * embedded document 场景匹配（Json格式表示包含关系，一对多，如Order等Model）
  * 弱一致性，保证了高性能（对于Payment等场景还是需要使用支持事务的数据库）
  * 横向扩展能力
  * [Why Use MongoDB](https://www.mongodb.com/why-use-mongodb)
  * [41 | MongoDB应用场景及选型](https://time.geekbang.org/course/detail/100040001-193615)
  * [Indexes](https://docs.mongodb.com/manual/indexes/)




* **缓存一致性如何解决（Shopee）**



* **建索引的策略（如 A,B,C三个字段，常用SQL 语句为 SELECT A,B,C where B=80 AND C > 200, SELECT A,B,C where A=50 AND B=80 AND C = 200，如何分别建立索引）（Shopee）**
  * 最左匹配原则 -- 联合索引的B+Tree是按照第一个关键字进行索引排列的，遇到范围查询就停止匹配
  * [【原创】面试官:谈谈你对mysql联合索引的认识？ ](https://www.cnblogs.com/rjzheng/p/12557314.html)



* **有哪些常用的负载均衡算法和实现（Shopee）**

  * [What Is Load Balancing?](https://www.nginx.com/resources/glossary/load-balancing/)
  * [Types of load balancing algorithms](https://www.cloudflare.com/zh-cn/learning/performance/types-of-load-balancing-algorithms/)

  

* **DDD的应用实践（WishPost领域模型的设计）**

  * 物流服务（数据和行为，首/中/末，国家），物流商的Client（特别的校验和处理逻辑）等
  * 有哪些领域，怎么划分的，依据是什么
  * [领域驱动设计在互联网业务开发中的实践](https://tech.meituan.com/2017/12/22/ddd-in-practice.html)



* **高并发访问下如何保证用户名不冲突，比如多个用户同时创建同一个用户名（拼多多）** 



* **为什么要用双亲委派模型，有没有别的实现方式，或者说Java为什么要这么设计？（阿里）**



* **从Java内存模型的角度解释一下volatile（华泰证券）**

