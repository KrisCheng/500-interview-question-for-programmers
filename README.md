# 500-interview-question-for-programmers

## 概述

本代码仓用于记录个人平时面试和学习时碰到的一些有价值的问题，所有问题均为我真实碰到过且思考过，一律采用问答形式，答案也只是我个人的理解和整理，不一定正确（未贴答案为还没来得及弄 Orz...），欢迎指正。

希望以此来保持个人知识体系的扎实性，所以就不是什么基础大全，面试突击，更多是个人对某些问题的总结（标题只是唬人的~~），欢迎Star，可配合同目录下 KnowledgeStructure 同步使用，供所有正在找工作的小伙伴们参考（500只是一个数，切莫抬杠）。

## Java

### Spring 相关

* **描述Spring的IOC**
	* IOC是一种思想，并非一个具体技术。
	* 好处 --> 让你脱离对依赖对象的维护，只需要随用随取，不需要关心依赖对象的任何过程。
	* “反转” --> 由容器来帮忙创建及注入依赖对象。
	* 实现 --> 依赖注入
		* 谁依赖于谁：当然是应用程序依赖于IoC容器；
		* 为什么需要依赖：应用程序需要IoC容器来提供对象需要的外部资源；
		* 谁注入谁：很明显是IoC容器注入应用程序某个对象，应用程序依赖的对象；
		* 注入了什么：就是注入某个对象所需要的外部资源（包括对象、资源、常量数据）。
	* [IoC-spring 的灵魂(带你轻松理解IOC思想及bean对象的生成过程)](https://juejin.im/post/593386ca2f301e00584f8036)
	* [【第二章】 IoC 之 2.1 IoC基础 ——跟我学Spring3](https://jinnianshilongnian.iteye.com/blog/1413846)	

* **描述Spring的AOP**
	* AOP的理念 --> 就是将分散在各个业务逻辑代码中 相同的代码 通过 **横向切割** 的方式抽取到一个独立的模块中（模块化）。
	* Spring AOP 实现 --> 动态代理
		* 好处 --> 显示地声明在何处如何应用该行为，有效减少代码冗余，让类更加关注自身主要功能
		* @Aspect --> 注解来声明通知方法
	* [《Spring设计思想》AOP实现原理（基于JDK和基于CGLIB）](https://blog.csdn.net/luanlouis/article/details/51155821)（还没看）
	* 《Spring实战（第四版）》
	* [Spring AOP就是这么简单啦](https://juejin.im/post/5b06bf2df265da0de2574ee1)


* **简述Spring Boot框架**
	* 核心
		* 自动配置
		* 起步依赖
	* 从本质上来说，Spring Boot就是Spring，它做了那些没有它你自己也会去做的Spring Bean配置；
	* 《Spring Boot实战》前三章


* **什么是JPA**
	* [Java持久化API Wiki](https://zh.wikipedia.org/wiki/Java%E6%8C%81%E4%B9%85%E5%8C%96API)


* **什么是Bean**
	* 在 Spring 中，构成应用程序主干并由Spring IoC容器管理的对象称为bean。bean是一个由Spring IoC容器实例化、组装和管理的对象。
	* [第37讲 | 谈谈Spring Bean的生命周期和作用域？](https://time.geekbang.org/column/article/12472)
	* [Spring Bean是什么？](https://www.awaimai.com/2596.html)


* **什么是Spring注解，以及Spring中有哪些常用的注解**
	* 注解 --> 减少配置文件内容
	* [精进Spring—Spring常用注解](https://blog.csdn.net/u010648555/article/details/76299467)（常见注解）

### 语法相关

* **乐观锁与悲观锁的概念，常见实现**
	* 乐观锁适用于**多读**的应用类型，这样可以提高吞吐量 / 悲观锁适合于**多写**
	* 乐观锁 --> 常见实现：CAS算法
		* CAS 算法缺点：
			* ABA 问题
	* [何谓悲观锁与乐观锁](https://github.com/Snailclimb/JavaGuide/blob/master/docs/essential-content-for-interview/%E9%9D%A2%E8%AF%95%E5%BF%85%E5%A4%87%E4%B9%8B%E4%B9%90%E8%A7%82%E9%94%81%E4%B8%8E%E6%82%B2%E8%A7%82%E9%94%81.md)

	
* **字符串相关问题**
	* StringBuffer --> 线程安全 / StringBuilder --> 非线程安全
	* [第5讲 | String、StringBuffer、StringBuilder有什么区别？](https://time.geekbang.org/column/article/7349)


* **什么是序列化（Serialization）和反序列化**
	* 对象序列化机制（object serialization）是java语言内建的一种对象持久化方式，通过对象序列化，可以将对象的状态信息保存未字节数组，并且可以在有需要的时候将这个字节数组通过反序列化的方式转换成对象，对象的序列化可以很容易的在JVM中的活动对象和字节数组（流）之间进行转换。
	* [Java对象的序列化（Serialization）和反序列化详解](https://blog.csdn.net/yaomingyang/article/details/79321939)

	
* **Java中父类和子类初始化顺序**
	* 1. 父类中静态成员变量和静态代码块
	* 2. 子类中静态成员变量和静态代码块
	* 3. 父类中普通成员变量和代码块，父类的构造函数
	* 4. 子类中普通成员变量和代码块，子类的构造函数
	* (其中“和”字两端的按照代码先后顺序执行。)
	* [java中父类和子类初始化顺序](https://blog.csdn.net/yuxin6866/article/details/53107578) 


* **什么是反射以及反射有什么具体应用**
	* Java反射机制是在运行状态中，对于任意一个类，都能够知道这个类的所有属性和方法；对于任意一个对象，都能够调用它的任意一个方法和属性；这种动态获取的信息以及动态调用对象的方法的功能称为java语言的反射机制；
	* “框架设计的灵魂” --> 如：Spring 通过 XML 配置模式装载 Bean 的过程；
	* [什么是反射机制？反射机制的应用场景有哪些？](https://github.com/Snailclimb/JavaGuide/blob/master/docs/essential-content-for-interview/MostCommonJavaInterviewQuestions/%E7%AC%AC%E4%BA%8C%E5%91%A8(2018-8-13).md#%E4%BB%80%E4%B9%88%E6%98%AF%E5%8F%8D%E5%B0%84%E6%9C%BA%E5%88%B6%E5%8F%8D%E5%B0%84%E6%9C%BA%E5%88%B6%E7%9A%84%E5%BA%94%E7%94%A8%E5%9C%BA%E6%99%AF%E6%9C%89%E5%93%AA%E4%BA%9B)

	
### 集合框架
		
* **HashMap 和 TreeMap 的区别**
	* HashMap通过hashcode对其内容进行快速查找，而 TreeMap中所有的元素都保持着某种固定的顺序，如果你需要得到一个有序的结果你就应该使用TreeMap（HashMap中元素的排列顺序是不固定的）；
	* HashMap 允许使用 null 值和 null 键，而 TreeMap 不可以；
	* 实现:
		* HashMap --> HashMap实际上是一个“链表散列”的数据结构，即数组和链表的结合体；如果追加节点后，链表数量 >= 8，则转化为红黑树；
		* TreeMap --> 红黑树
	* HashMap 非线程安全 / TreeMap 非线程安全
	* [HashMap和TreeMap区别详解以及底层实现](https://blog.csdn.net/xlgen157387/article/details/47907721)
	* [第9讲 | 对比Hashtable、HashMap、TreeMap有什么不同？](https://time.geekbang.org/column/article/8053)

	
* **描述 HashMap 的底层实现**
	* JDK < 1.8 --> 数组和链表；
	* JDK >= 1.8 --> 链表长度大于阈值（默认为8）时，将链表转化为红黑树，以减少搜索时间；
	* 具体方法 get(), put()
	* [HashMap 简介](https://github.com/Snailclimb/JavaGuide/blob/master/docs/java/collection/HashMap.md)


* **HashSet 如何判断重复元素**
	* 首先会调用Object的hashCode方法判hashCode是否已经存在，如不存在则直接插入元素； 
	* 如果已存在则调用Object对象的equals方法判断是否返回true， 如果为true则说明元素已经存在，如为false则插入元素。 
	* Java对象的eqauls方法和hashCode方法是这样规定的：
		* 1、相等（相同）的对象必须具有相等的哈希码（或者散列码）。
		* 2、如果两个对象的hashCode相同，它们并不一定相同。
	* [HashSet重复元素判断](https://itfafa.iteye.com/blog/1698690) 
	* [Java提高篇——equals()与hashCode()方法详解](https://www.cnblogs.com/Qian123/p/5703507.html)


### Java内存模型相关
	
* **描述Java内存模型**
	* JVM内存区域划分
		* 程序计数器 --> 它的作用可以看做是当前线程所执行的字节码的行号指示器;
		* Java 虚拟机栈 --> 保存一个个栈帧（Stack Frame），对应着一次次的Java方法调用；
		* 堆 --> 几乎所有的 **对象实例** 都在这里分配内存;
		* 方法区（Method Area） --> 所有线程共享的一块内存区域，用于存储所谓的元（Meta）数据，如类结构信息，以及对应的运行时常量池、字段、方法代码等；
		* 运行时常量池 --> 存放各种常量信息；
		* 本地方法栈 --> 为虚拟机使用到的Native方法服务;
	* [第25讲 | 谈谈JVM内存区域的划分，哪些区域可能发生OutOfMemoryError?](https://time.geekbang.org/column/article/10192)
	* [jvm系列(二):JVM内存结构](https://mp.weixin.qq.com/s?__biz=MzI4NDY5Mjc1Mg==&mid=2247483949&idx=1&sn=8b69d833bbc805e63d5b2fa7c73655f5&chksm=ebf6da52dc815344add64af6fb78fee439c8c27b539b3c0e87d8f6861c8422144d516ae0a837&scene=21#wechat_redirect)


* **描述Java的GC过程**
	* 对象是否存活
		* 引用计数
		* 可达性分析 --> GC Roots
	* 垃圾收集算法
		* 标记-清除算法（Mark-Sweep） --> 内存碎片化问题；
		* 复制算法（Copying） --> 将活着的对象复制到 to 区域，拷贝过程中将对象顺序放置，避免内存碎片化；
		* 标记-整理算法（Mark-Compact） --> 类似于标记-清除，但为了避免内存碎片化，在清理过程中移动对象，以确保移动后的对象占用连续的内存空间；
	* [第27讲 | Java常见的垃圾收集器有哪些？](https://time.geekbang.org/column/article/10513)
	* [jvm系列(三):GC算法 垃圾收集器](https://mp.weixin.qq.com/s?__biz=MzI4NDY5Mjc1Mg==&mid=2247483952&idx=1&sn=ea12792a9b7c67baddfaf425d8272d33&chksm=ebf6da4fdc815359869107a4acd15538b3596ba006b4005b216688b69372650dbd18c0184643&scene=21#wechat_redirect)

	
### 并发

* **描述Java下的并发编程**
	* 线程操作相关
	* [Java 多线程编程](https://www.runoob.com/java/java-multithreading.html)（线程的生命周期 && Java中创建线程的方法）

		
* **什么是线程安全**
	* [线程安全 Wiki](https://zh.wikipedia.org/wiki/%E7%BA%BF%E7%A8%8B%E5%AE%89%E5%85%A8)


* **join() 方法有什么用**
	* Thread.join把指定的线程加入到当前线程，可以将两个交替执行的线程合并为顺序执行的线程。比如在线程B中调用了线程A的Join()方法，直到线程A执行完毕后，才会继续执行线程B；
	* [Java多线程中join方法的理解](https://uule.iteye.com/blog/1101994)
	* [简谈Java的join()方法](https://www.cnblogs.com/techyc/p/3286678.html) 
	
	
* **sychronized关键字**
	* [Java线程同步：synchronized锁住的是代码还是对象](https://blog.csdn.net/xiao__gui/article/details/8188833) 

		
* [面向面试的Java并发基础整理](http://pengcheng.tech/2019/03/24/%e9%9d%a2%e5%90%91%e9%9d%a2%e8%af%95%e7%9a%84java%e5%b9%b6%e5%8f%91%e5%9f%ba%e7%a1%80%e6%95%b4%e7%90%86/) （个人初步总结）
* [Java并发编程学习路线](https://zhuanlan.zhihu.com/p/25577863)（学习思路篇）


## Python

* **用map/reduce实现数组求和**
	* [map/reduce](https://www.liaoxuefeng.com/wiki/1016959663602400/1017329367486080)
	* map --> 将传入函数依次作用于序列中的每个元素，并把结果作为新的Iterator返回;
	* reduce --> 累积计算, 求和 ```reduce(lambda x, y : x + y, [1,2,3,4,5])```.


* **实现一个lambda表达式**
	* 匿名函数，个人理解为一种语法糖
	* [Lambda 表达式有何用处？如何使用？](https://www.zhihu.com/question/20125256)


* Python如何实现真正的多线程


* 给一段Python代码，有哪些优化思路和策略


* 如何写一个程序计算一段Python代码的耗时


* Python爬虫中存在环引用该如何处理


* 描述Python的迭代器和生成器


## 操作系统

* **进程/线程的概念和区别**
	* 进程 --> 计算机中已运行的程序，具有一定独立功能的程序关于某个数据集合上的一次运行活动，进程是系统进行资源分配和调度的一个独立单位；
	* 线程 --> 操作系统能够进行运算调度的最小单位，它被包含在进程之中，是进程中的实际运作单位。
	* 进程和线程都是一个时间段的描述，是CPU工作时间段的描述，不过是颗粒大小不同；
	* 一个程序至少有一个进程,一个进程至少有一个线程；
	* [腾讯面试题04.进程和线程的区别？](https://blog.csdn.net/mxsgoden/article/details/8821936)
	* [进程与线程的一个简单解释](http://www.ruanyifeng.com/blog/2013/04/processes_and_threads.html)
	* [线程和进程的区别是什么？](https://www.zhihu.com/question/25532384)
	* [线程 Wiki](https://zh.wikipedia.org/wiki/%E7%BA%BF%E7%A8%8B)
	* [进程 Wiki](https://zh.wikipedia.org/wiki/%E8%A1%8C%E7%A8%8B)

	
* **Java中如何使用线程池**
	* [Java并发编程：线程池的使用](https://www.cnblogs.com/dolphin0520/p/3932921.html)
	* [深入理解 Java 线程池：ThreadPoolExecutor](https://juejin.im/entry/58fada5d570c350058d3aaad)


* **描述操作系统的启动过程**
	* 步骤 
		* BIOS
		* 主引导记录（Master boot record）
		* 硬盘启动
		* 操作系统
	* [计算机是如何启动的？](http://www.ruanyifeng.com/blog/2013/02/booting.html) 
	

* **用一门编程语言（如Java）实现一个死锁**
	* [死锁 Wiki](https://zh.wikipedia.org/wiki/%E6%AD%BB%E9%94%81)
	* [第18讲 | 什么情况下Java程序会产生死锁？如何定位、修复？](https://time.geekbang.org/column/article/9266)
	* [JAVA实现的一个简单的死锁（附解释）](https://blog.csdn.net/zll793027848/article/details/8670546) 


* **如何判断内存泄漏**
	* 因为长生命周期持有它的引用而导致不能被回收，这就是Java中内存泄漏的发生场景；
	* [Java内存泄漏分析和解决](https://www.jianshu.com/p/54b5da7c6816)


* **什么是系统调用**
	* 指运行在用户空间的程序向操作系统内核请求需要更高权限运行的服务；
	* linux内核中设置了一组用于实现系统功能的子程序，称为系统调用。系统调用和普通库函数调用非常相似，只是系统调用由操作系统核心提供，运行于**内核态**，而普通的函数调用由函数库或用户自己提供，运行于**用户态**；
	* [系统调用 Wiki](https://zh.wikipedia.org/wiki/%E7%B3%BB%E7%BB%9F%E8%B0%83%E7%94%A8)
	* [Linux系统调用详解（实现机制分析）--linux内核剖析（六）](https://blog.csdn.net/gatieme/article/details/50779184)


## 数据结构和算法

### 排序相关

* 给定一个无符号，包含10亿个数的数组，如何取出前100个数


* 如何找到一个无序数组的中位数


* 如何给一个很大的无序数组去重


* Java自带的 sort() 方法是如何实现的


* 手写快排和复杂度分析


* 手写堆排和复杂度分析


### 树/链表相关

* **二叉树的遍历**
	* 通过引入一种新的数据结构形成通用解法（Node + 是否访问标识符）
	* 用一个队列添加/删除节点
	* 用一个list存储节点
	* [二叉树的前序遍历](https://leetcode-cn.com/problems/binary-tree-preorder-traversal/)
	* [二叉树的中序遍历](https://leetcode-cn.com/problems/binary-tree-inorder-traversal/)
	* [二叉树的后序遍历](https://leetcode-cn.com/problems/binary-tree-postorder-traversal/)

	
* **求二叉树的深度（非递归实现）**
	* 引入一个队列，逐层遍历
	* [二叉树的深度（递归和非递归）---java实现](https://blog.csdn.net/snow_7/article/details/51818580)


* 红黑树描述及其复杂度分析（插入/查找）


* 非递归从左至右打印一颗二叉树中的所有路径


* 如何将一棵非平衡二叉树转化成平衡二叉树


### 字符串

* 如何找出一个字符串中的最大不重复子串


### 动态规划

* 描述01背包问题


### 其他

* 实现一个二叉搜索树的迭代器，包括next()和hasNext()方法


## 数据库

### 基本理论

* **描述事务隔离的级别**
	* Serializable【可避免脏读，不可重复读，虚读】
	* Repeatable read【可避免脏读，不可重复读】
	* Read committed【可避免脏读】
	* Read uncommitted【级别最低，什么都避免不了】
	* [数据库事务隔离级别-- 脏读、幻读、不可重复读（清晰解释）](https://blog.csdn.net/jiesa/article/details/51317164)


* **delete、 drop、truncate 的区别**
	* drop 直接删掉表（不再需要一张表的时候，用drop）；
	* truncate 删除的是表中的数据，再插入数据时自增长的数据id又重新从1开始（保留表而删除所有数据的时候用truncate）；
	* delete 删除表中数据，可以在后面添加where字句（想删除部分数据行时候，用delete，并且带上where子句）。 
	* [SQL truncate 、delete与drop区别](https://www.cnblogs.com/8765h/archive/2011/11/25/2374167.html)


* **索引是什么，有哪些常见索引，以及为什么MySQL使用B+树做索引**
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


* **对于海量数据，如何提高查询效率（数据库优化策略）**
	* [优化1——数据库优化面试题](https://blog.csdn.net/u010796790/article/details/52194850) 


* **第一/第三/BC范式，以及我们实际建表时为什么要设计冗余字段，同时设计冗余字段会带来什么问题** （阿里面试官问的，我觉得这个问题很好，但总感觉不是有点自相矛盾么 Orz...）
	* 区分快照和冗余
	* [数据库设计冗余字段问题？](https://www.zhihu.com/question/50662784)
	* [如何解释关系数据库的第一第二第三范式？](https://www.zhihu.com/question/24696366) 


### SQL语句相关

* **各种join操作的区别（left, right, inner join）**
	* [mysql join操作](https://www.cnblogs.com/ggjucheng/archive/2012/11/06/2757972.html)

	
* **找出在表A中但不在表B中的记录（根据某一个共同的column）**
	* [查询A、B表中，A表中B表没有的数据](https://blog.csdn.net/long636/article/details/51733273)（三种方法）

	 

## 计算机网络

* 用Socket描述TCP的三次握手
	*  


* 描述HTTPS的加密过程


* HTTP代理的实现


* 网络间的进程如何表示


* 从客户端发送请求，该请求是如何传到服务端的


* TCP和UDP的区别



## Linux相关

* 常见的Linux指令


## 编程之美

* 实现一个线程安全的单例模式


* 设计一个方案，提供不同算法调用接口（参数即为需要调用的方法名）（设计模式实际应用）



## 其他

* git rebase 和 git merge 有什么区别


* git fetch 和 git pull 有什么区别


* 描述 git 中的 cherry-pick 指令

* **如何设计一个秒杀系统**
	* [Java开发面试：高并发秒杀系统如何设计与优化](https://blog.csdn.net/CSDN_Terence/article/details/77744042)
	* [如何设计一个秒杀系统](https://blog.csdn.net/suifeng3051/article/details/52607544)