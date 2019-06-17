# 500-interview-question-for-programmers

## 概述

本代码仓用于记录个人平时面试和学习时碰到的一些有价值问题，所有问题均为我真实碰到过且思考过，一律采用问答形式，答案也只是我个人的理解，不一定正确（未贴答案为还没来得及弄 Orz...），欢迎指正。

希望以此来保持个人知识体系的扎实性，所以就不是什么基础大全，面试突击，更多是个人对某些问题的总结了（标题只是唬人的~~），欢迎Star，可配合同目录下 KnowledgeStructure 同步使用，供所有正在找工作的小伙伴们参考（500只是一个数，切莫抬杠）。

## Java

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
	* Spring AOP 原理 --> 动态代理
	* 好处 --> 显示地声明在何处如何应用该行为，有效减少代码冗余，让类更加关注自身主要功能
	* @Aspect --> 注解来声明通知方法
	* 《Spring实战（第四版）》
	* [Spring AOP就是这么简单啦](https://juejin.im/post/5b06bf2df265da0de2574ee1)


* **描述Spring Boot框架**
	* 核心
		* 自动配置
		* 起步依赖
	* 从本质上来说，Spring Boot就是Spring，它做了那些没有它你自己也会去做的Spring Bean配置；
	* 
	* 《Spring Boot实战》


* **什么是Bean**
	* “在 Spring 中，构成应用程序主干并由Spring IoC容器管理的对象称为bean。bean是一个由Spring IoC容器实例化、组装和管理的对象。”
	* [第37讲 | 谈谈Spring Bean的生命周期和作用域？](https://time.geekbang.org/column/article/12472)
	* [Spring Bean是什么？](https://www.awaimai.com/2596.html)


* **什么是Spring注解，以及Spring中有哪些常用的注解**
	* 注解 --> 减少配置文件内容
	* [精进Spring—Spring常用注解](https://blog.csdn.net/u010648555/article/details/76299467)（常见注解）


* **乐观锁与悲观锁的概念，常见实现**
	* 乐观锁适用于**多读**的应用类型，这样可以提高吞吐量 / 悲观锁适合于**多写**
	* 乐观锁 --> 常见实现：CAS算法
		* CAS 算法缺点：
			* ABA 问题
	* [何谓悲观锁与乐观锁](https://github.com/Snailclimb/JavaGuide/blob/master/docs/essential-content-for-interview/%E9%9D%A2%E8%AF%95%E5%BF%85%E5%A4%87%E4%B9%8B%E4%B9%90%E8%A7%82%E9%94%81%E4%B8%8E%E6%82%B2%E8%A7%82%E9%94%81.md)

	
* **HashMap和TreeMap的区别**
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


* **什么是反射以及反射有什么具体应用**
	* Java反射机制是在运行状态中，对于任意一个类，都能够知道这个类的所有属性和方法；对于任意一个对象，都能够调用它的任意一个方法和属性；这种动态获取的信息以及动态调用对象的方法的功能称为java语言的反射机制；
	* “框架设计的灵魂” --> 如：Spring 通过 XML 配置模式装载 Bean 的过程；
	* [什么是反射机制？反射机制的应用场景有哪些？](https://github.com/Snailclimb/JavaGuide/blob/master/docs/essential-content-for-interview/MostCommonJavaInterviewQuestions/%E7%AC%AC%E4%BA%8C%E5%91%A8(2018-8-13).md#%E4%BB%80%E4%B9%88%E6%98%AF%E5%8F%8D%E5%B0%84%E6%9C%BA%E5%88%B6%E5%8F%8D%E5%B0%84%E6%9C%BA%E5%88%B6%E7%9A%84%E5%BA%94%E7%94%A8%E5%9C%BA%E6%99%AF%E6%9C%89%E5%93%AA%E4%BA%9B)


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

	
* **描述Java内存模型**
	* JVM内存区域划分
		* 程序计数器 --> 它的作用可以看做是当前线程所执行的字节码的行号指示器;
		* Java 虚拟机栈 --> 保存一个个栈帧（Stack Frame），对应着一次次的Java方法调用；
		* 堆 --> 几乎所有的**对象实例**都在这里分配内存;
		* 方法区（Method Area） --> 所有线程共享的一块内存区域，用于存储所谓的元（Meta）数据，如类结构信息，以及对应的运行时常量池、字段、方法代码等；
		* 运行时常量池 --> 存放各种常量信息；
		* 本地方法栈 --> 为虚拟机使用到的Native方法服务;
		* [第25讲 | 谈谈JVM内存区域的划分，哪些区域可能发生OutOfMemoryError?](https://time.geekbang.org/column/article/10192)
		* [jvm系列(二):JVM内存结构](https://mp.weixin.qq.com/s?__biz=MzI4NDY5Mjc1Mg==&mid=2247483949&idx=1&sn=8b69d833bbc805e63d5b2fa7c73655f5&chksm=ebf6da52dc815344add64af6fb78fee439c8c27b539b3c0e87d8f6861c8422144d516ae0a837&scene=21#wechat_redirect)

		
* 描述Java语境下的并发编程



## Python

* **用map/reduce实现数组求和**
	* [map/reduce](https://www.liaoxuefeng.com/wiki/1016959663602400/1017329367486080)
	* map --> 将传入函数依次作用于序列中的每个元素，并把结果作为新的Iterator返回;
	* reduce --> 累积计算, 求和 ```reduce(lambda x, y : x + y, [1,2,3,4,5])```.

* **实现一个lambda表达式**
	* 匿名函数，个人理解为一种语法糖
	* [Lambda 表达式有何用处？如何使用？](https://www.zhihu.com/question/20125256)

* Python如何实现真正的多线程


* 一段Python代码，有哪些优化策略


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

	
* Java中如何创建线程池


* **描述操作系统的启动过程**
	* BIOS
	* 主引导记录（Master boot record）
	* 硬盘启动
	* 操作系统
	* [计算机是如何启动的？](http://www.ruanyifeng.com/blog/2013/02/booting.html) 
	

* 用一门编程语言（如Java）实现一个死锁


* 如何判断内存泄漏


* **什么是系统调用**
	* 指运行在用户空间的程序向操作系统内核请求需要更高权限运行的服务；
	* linux内核中设置了一组用于实现系统功能的子程序，称为系统调用。系统调用和普通库函数调用非常相似，只是系统调用由操作系统核心提供，运行于**内核态**，而普通的函数调用由函数库或用户自己提供，运行于**用户态**；
	* [系统调用 Wiki](https://zh.wikipedia.org/wiki/%E7%B3%BB%E7%BB%9F%E8%B0%83%E7%94%A8)
	* [Linux系统调用详解（实现机制分析）--linux内核剖析（六）](https://blog.csdn.net/gatieme/article/details/50779184)


## 数据结构与算法

* 给定一个无符号，包含10亿个数的数组，如何取出前100个数


* 如何找到一个无序数组的中位数


* 如何给一个很大的无序数组去重


* Java中的 sort() 方法是如何实现的


* 实现一个二叉搜索树的迭代器，包括next()和hasNext()方法


* 手写快排和复杂度分析


* 手写堆排和复杂度分析


* 红黑树描述及其复杂度分析（插入/查找）


* 第一/第三/BC范式，以及我们实际建表时为什么要设计冗余字段，同时设计冗余字段会带来什么问题


* 非递归从左至右打印一颗二叉树中的所有路径


* 描述01背包问题


* 如何将一棵非平衡二叉树转化成平衡二叉树


* 如何从一个字符串中找出最大不重复子串



## 数据库

* 描述事务隔离的级别


* 找出在表A中但不在表B中的记录（根据一个column）


* delete、 drop、truncate 的区别


* 为什么MySQL使用B+树做索引


* 对于海量数据，如何提高查询效率



## 计算机网络

* 用Socket描述TCP的三次握手


* 描述HTTPS的加密过程


* HTTP代理的实现


* 网络间的进程如何表示


* 从客户端发送请求，该请求是如何传到服务端的


* TCP和UDP的区别



## Linux相关

* 常见的Linux指令


## 编程之美

* 手写一个线程安全的单例模式


* 设计一个方案，提供不同算法调用接口（参数即为需要调用的方法名）（设计模式实际应用）



## 其他

* git rebase 和 git merge 有什么区别


* git fetch 和 git pull 有什么区别

