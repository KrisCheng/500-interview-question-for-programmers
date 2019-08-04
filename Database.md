### 数据库理论

* **描述事务隔离的级别（野村证券/远景智能）**
	* Serializable（序列化） --> 可避免脏读，不可重复读，幻读
	* Repeatable read（可重复读） --> 可避免脏读，不可重复读，但可能出现幻读 
	* Read committed（已提交读） --> 可避免脏读，但是可能会造成不可重复读
	* Read uncommitted（未提交读） --> 级别最低，什么都避免不了
	* 脏读 --> 当一个事务允许读取另外一个事务修改但未提交的数据时，就可能发生脏读
	* 不可重复度 --> 在一次事务中，当一行数据获取两遍得到不同的结果表示发生了“不可重复读”
	* 幻读 --> 在事务执行过程中，当两个完全相同的查询语句执行得到不同的结果集。这种现象称为幻读
	* [ACID Wiki](https://zh.wikipedia.org/wiki/ACID)
	* [事务隔离 Wiki](https://zh.wikipedia.org/wiki/%E4%BA%8B%E5%8B%99%E9%9A%94%E9%9B%A2)
	* [数据库事务隔离级别-- 脏读、幻读、不可重复读（清晰解释）](https://blog.csdn.net/jiesa/article/details/51317164)


* MySQL是如何实现隔离级别的（如可重复度是怎么实现的）（拼多多）*`TODO`*


* **delete、 drop、truncate 的区别（PayPal）**
	* drop 直接删掉表（不再需要一张表的时候，用drop）；
	* truncate 删除的是表中的数据，再插入数据时自增长的数据id又重新从1开始（保留表而删除所有数据的时候用truncate，实际是删除原来的表并重建一张新表）；
	* delete 删除表中数据，可以在后面添加where字句（想删除部分数据行时候，用delete，并且带上where子句）。 
	* [SQL truncate 、delete与drop区别](https://www.cnblogs.com/8765h/archive/2011/11/25/2374167.html)


* **索引是什么，有哪些常见索引，以及为什么MySQL使用B+树做索引（头条）**
	* 索引 --> 一种数据结构
	* B+ 树做索引：
		* AVL, 红黑树等二叉树，其查找过程中要进行许多次的磁盘读取操作，非常耗时；
		* B树
			* B+树的层级更少：相较于B树B+每个非叶子节点存储的关键字数更多，树的层级更少所以查询数据更快；
			* B+树查询速度更稳定：B+所有关键字数据地址都存在叶子节点上，所以每次查找的次数都相同所以查询速度要比B树更稳定;
			* B+树天然具备排序功能：B+树所有的叶子节点数据构成了一个有序链表，在查询大小区间的数据时候更方便，数据紧密性很高，缓存的命中率也会比B树高；
			* B+树全节点遍历更快：B+树遍历整棵树只需要遍历所有的叶子节点即可，而不需要像B树一样需要对每一层进行遍历，这有利于数据库做全表扫描。
	* [数据库索引到底是什么，是怎样工作的？](https://blog.csdn.net/weiliangliang111/article/details/51333169)
	* [一步步分析为什么B+树适合作为索引的结构](https://blog.csdn.net/weixin_30531261/article/details/79312676)
	* [平衡二叉树、B树、B+树、B*树 理解其中一种你就都明白了](https://zhuanlan.zhihu.com/p/27700617)


* 聚集索引和非聚集索引的区别（拼多多）*`TODO`*


* **对于海量数据，如何提高查询效率（数据库优化策略）（野村证券）**
	* [优化1——数据库优化面试题](https://blog.csdn.net/u010796790/article/details/52194850) 


* **第一/第三/BC范式，以及我们实际建表时为什么要设计冗余字段，同时设计冗余字段会带来什么问题（阿里）**
	* 区分快照和冗余
	* [数据库设计冗余字段问题？](https://www.zhihu.com/question/50662784)
	* [如何解释关系数据库的第一第二第三范式？](https://www.zhihu.com/question/24696366) 


### SQL语句相关

* **各种join操作的区别（left, right, inner join）**
	* [mysql join操作](https://www.cnblogs.com/ggjucheng/archive/2012/11/06/2757972.html)

	
* **找出在表A中但不在表B中的记录（根据某一个共同的column）（PayPal）**
	* [查询A、B表中，A表中B表没有的数据](https://blog.csdn.net/long636/article/details/51733273)（三种方法）
