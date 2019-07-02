# 500-interview-question-for-programmers

## 概述

本代码仓用于记录个人平时面试和学习时碰到的一些有价值的问题，所有问题均为我真实碰到过且思考过（部分附面试公司），一律采用问答形式，答案也只是我个人的理解和整理，不一定正确（未贴答案为还没来得及弄 Orz...），欢迎指正。

希望以此来保持个人知识体系的扎实性，所以就不是什么基础大全，面试突击，更多是个人对某些问题的总结（标题只是唬人的~~），欢迎Star，可配合同目录下 KnowledgeStructure 同步使用，供所有正在找工作的小伙伴们参考（500只是一个数，切莫抬杠）。

## Java

### Spring 相关

* **描述Spring的IoC**
	* IoC是一种思想，并非一个具体技术。
	* 好处 --> 让你脱离对依赖对象的维护，只需要随用随取，不需要关心依赖对象的任何过程。
	* “反转” --> 由容器来帮忙创建及注入依赖对象。
	* 实现 --> 依赖注入
		* 谁依赖于谁：当然是应用程序依赖于IoC容器；
		* 为什么需要依赖：应用程序需要IoC容器来提供对象需要的外部资源；
		* 谁注入谁：很明显是IoC容器注入应用程序某个对象，应用程序依赖的对象；
		* 注入了什么：就是注入某个对象所需要的外部资源（包括对象、资源、常量数据）。
	* [IoC-spring 的灵魂(带你轻松理解IOC思想及bean对象的生成过程)](https://juejin.im/post/593386ca2f301e00584f8036)
	* [【第二章】 IoC 之 2.1 IoC基础 ——跟我学Spring3](https://jinnianshilongnian.iteye.com/blog/1413846)


* **描述Spring的AOP（小红书）**
	* AOP的理念 --> 就是将分散在各个业务逻辑代码中 相同的代码 通过 **横向切割** 的方式抽取到一个独立的模块中（模块化）。
	* 好处 --> 显示地声明在何处如何应用该行为，有效减少代码冗余，让类更加关注自身主要功能。
	* 基本概念：
		* 通知（advice） --> 切面的工作被称为通知，定义了切面是什么以及何时被使用
		* 连接点（join point） --> 应用执行过程中能够插入切面的一个点，可以是方法调用时，抛出异常时等等...
		* 切点（pointcut） --> 需要应用切面的方法（具体定位的连接点）
		* 切面（aspect） --> 切面是 通知 和 切点 的结合，共同定义：是什么，在何时和何处完成其功能
		* 织入(weaving) --> 把切面应用到目标函数的过程
	* Spring AOP 实现：
		* Java JDK动态代理
		* CGLIB动态代理
	* [关于 Spring AOP (AspectJ) 你该知晓的一切](https://blog.csdn.net/javazejian/article/details/56267036)（AOP入门 + 应用场景 + Spring中的基本实现）
	* [《Spring设计思想》AOP设计基本原理](https://blog.csdn.net/luanlouis/article/details/51095702)（从程序运行角度解释AOP的工作原理）
	* [《Spring设计思想》AOP实现原理（基于JDK和基于CGLIB）](https://blog.csdn.net/luanlouis/article/details/51155821) （Spring AOP的完整实现过程，未细看）
	* 《Spring实战（第四版）》第四章
	* [Spring AOP就是这么简单啦](https://juejin.im/post/5b06bf2df265da0de2574ee1)（可在面试前看的纯干货）


* **什么是Bean**
	* 在 Spring 中，构成应用程序主干并由Spring IoC容器管理的对象称为bean。bean是一个由Spring IoC容器实例化、组装和管理的对象。
	* [第37讲 | 谈谈Spring Bean的生命周期和作用域？](https://time.geekbang.org/column/article/12472)
	* [Spring Bean是什么？](https://www.awaimai.com/2596.html)


* **简述Spring Boot框架**
	* 核心
		* 自动配置
		* 起步依赖
	* 从本质上来说，Spring Boot就是Spring，它做了那些没有它你自己也会去做的Spring Bean配置；
	* 《Spring Boot实战》前三章


* **什么是JPA**
	* [Java持久化API Wiki](https://zh.wikipedia.org/wiki/Java%E6%8C%81%E4%B9%85%E5%8C%96API)


* **什么是Spring注解，以及Spring中有哪些常用的注解（阿里）**
	* 注解 --> 减少配置文件内容
	* [秒懂，Java 注解 （Annotation）你可以这样学](https://blog.csdn.net/briblue/article/details/73824058)（简单理解， 注解 --> 标签）
	* [精进Spring—Spring常用注解](https://blog.csdn.net/u010648555/article/details/76299467)（常见注解）


### Java语法相关
	
* **字符串相关问题**
	* StringBuffer --> 线程安全 / StringBuilder --> 非线程安全
	* [第5讲 | String、StringBuffer、StringBuilder有什么区别？](https://time.geekbang.org/column/article/7349)


* **什么是序列化（Serialization）和反序列化（小红书）**
	* 序列化：把对象转换为字节序列的过程称为对象的序列化。
	* 反序列化：把字节序列恢复为对象的过程称为对象的反序列化。
	* [Java对象的序列化（Serialization）和反序列化详解](https://blog.csdn.net/yaomingyang/article/details/79321939)
	* [Java 之 Serializable 序列化和反序列化的概念,作用的通俗易懂的解释](https://blog.csdn.net/qq_27093465/article/details/78544505)

	
* **Java中父类和子类初始化顺序（小红书）**
	* 优先级：
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
		
* **HashMap 和 TreeMap 的区别（PayPal）**
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


* **HashSet 如何判断重复元素（小红书）**
	* 首先会调用 Object 的 hashCode 方法判 hashCode 是否已经存在，如不存在则直接插入元素； 
	* 如果已存在则调用 Object 对象的 equals 方法判断是否返回true， 如果为true则说明元素已经存在，如为false则插入元素。 
	* Java对象的 eqauls 方法和 hashCode 方法是这样规定的：
		* 1、相等（相同）的对象必须具有相等的哈希码（或者散列码）。
		* 2、如果两个对象的hashCode相同，它们并不一定相同。
	* [HashSet重复元素判断](https://itfafa.iteye.com/blog/1698690) 
	* [Java提高篇——equals()与hashCode()方法详解](https://www.cnblogs.com/Qian123/p/5703507.html)


### Java内存模型相关
	
* **描述Java内存模型（阿里）**
	* JVM内存区域划分
		* 程序计数器 --> 它的作用可以看做是当前线程所执行的字节码的行号指示器;
		* Java 虚拟机栈 --> 保存一个个栈帧（Stack Frame），对应着一次次的Java方法调用；
		* 堆 --> 几乎所有的 **对象实例** 都在这里分配内存;
		* 方法区（Method Area） --> 所有线程共享的一块内存区域，用于存储所谓的元（Meta）数据，如类结构信息，以及对应的运行时常量池、字段、方法代码等；
		* 运行时常量池 --> 存放各种常量信息；
		* 本地方法栈 --> 为虚拟机使用到的Native方法服务;
	* [第25讲 | 谈谈JVM内存区域的划分，哪些区域可能发生OutOfMemoryError?](https://time.geekbang.org/column/article/10192)
	* [jvm系列(二):JVM内存结构](https://mp.weixin.qq.com/s?__biz=MzI4NDY5Mjc1Mg==&mid=2247483949&idx=1&sn=8b69d833bbc805e63d5b2fa7c73655f5&chksm=ebf6da52dc815344add64af6fb78fee439c8c27b539b3c0e87d8f6861c8422144d516ae0a837&scene=21#wechat_redirect)


* **描述Java的GC过程（DaoCloud）**
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

* **描述Java下的并发编程（阿里）**
	* 线程操作相关
	* [Java 多线程编程](https://www.runoob.com/java/java-multithreading.html)（线程的生命周期 && Java中创建线程的方法）

		
* **什么是线程安全**
	* [线程安全 Wiki](https://zh.wikipedia.org/wiki/%E7%BA%BF%E7%A8%8B%E5%AE%89%E5%85%A8)


* **join() 方法有什么用**
	* Thread.join把指定的线程加入到当前线程，可以将两个交替执行的线程合并为顺序执行的线程。比如在线程B中调用了线程A的join()方法，直到线程A执行完毕后，才会继续执行线程B；
	* [Java多线程中join方法的理解](https://uule.iteye.com/blog/1101994)
	* [简谈Java的join()方法](https://www.cnblogs.com/techyc/p/3286678.html) 
	
	
* **sychronized关键字**
	* synchronized锁住的是括号里的对象，而不是代码
	* [Java线程同步：synchronized锁住的是代码还是对象](https://blog.csdn.net/xiao__gui/article/details/8188833) 


* **Java中如何使用线程池（阿里）**
	* 线程池的好处
		* 降低资源消耗 / 提高响应速度 / 提高线程的可管理性
	* 创使用方法
		* ThreadPoolExecutor类
			* 线程池中的每一个线程被封装成一个 Worker 对象，ThreadPool 维护的其实就是一组 Worker 对象
			* 一些主要参数
				* corePoolSize --> 核心线程数
				* maximumPoolSize --> 最大能创建的线程数（可以理解为当任务量突然过大时的一种补救措施）
				* workQueue --> 工作队列，为 BlockingQueue，用于存储等待执行的任务
	* [深入理解 Java 线程池：ThreadPoolExecutor](https://juejin.im/entry/58fada5d570c350058d3aaad)（ThreadPoolExecutor 源码和关键类分析）
	* [Java并发编程：线程池的使用](https://www.cnblogs.com/dolphin0520/p/3932921.html)（ThreadPoolExecutor 源码 和 基本用法）
	* [第21讲 | Java并发类库提供的线程池有哪几种？ 分别有什么特点？](https://time.geekbang.org/column/article/9712)（介绍 Executor 框架和从设计思想角度介绍ThreadPoolExecutor类）


* **乐观锁与悲观锁的概念，常见实现（阿里）** *TODO*
	* 乐观锁适用于**多读**的应用类型，这样可以提高吞吐量 / 悲观锁适合于**多写**
	* 乐观锁 --> 常见实现：CAS算法
		* CAS 算法缺点：
			* ABA 问题
	* [何谓悲观锁与乐观锁](https://github.com/Snailclimb/JavaGuide/blob/master/docs/essential-content-for-interview/%E9%9D%A2%E8%AF%95%E5%BF%85%E5%A4%87%E4%B9%8B%E4%B9%90%E8%A7%82%E9%94%81%E4%B8%8E%E6%82%B2%E8%A7%82%E9%94%81.md)


* [面向面试的Java并发基础整理](http://pengcheng.tech/2019/03/24/%e9%9d%a2%e5%90%91%e9%9d%a2%e8%af%95%e7%9a%84java%e5%b9%b6%e5%8f%91%e5%9f%ba%e7%a1%80%e6%95%b4%e7%90%86/) （个人初步总结，发现还是应付不了面试Orz...）
* [Java并发编程学习路线](https://zhuanlan.zhihu.com/p/25577863)（学习思路篇）


## Python

* **用map/reduce实现数组求和（PayPal）**
	* [map/reduce](https://www.liaoxuefeng.com/wiki/1016959663602400/1017329367486080)
	* map --> 将传入函数依次作用于序列中的每个元素，并把结果作为新的Iterator返回;
	* reduce --> 累积计算, 求和 ```reduce(lambda x, y : x + y, [1,2,3,4,5])```.


* **实现一个lambda表达式（头条）**
	* 匿名函数，个人理解为一种语法糖
	* [Lambda 表达式有何用处？如何使用？](https://www.zhihu.com/question/20125256)


* **Python如何实现真正的多线程（阿里/腾讯）** *TODO*
	* [Python 多线程](https://www.runoob.com/python/python-multithreading.html) 


* 给一段Python代码，有哪些优化思路和策略（阿里）


* 如何写一个程序计算一段Python代码的耗时（腾讯）


* Python爬虫中存在环引用该如何处理（阿里）


* **描述Python的迭代器和生成器（DaoCloud）** *TODO*
	* [Python3 迭代器与生成器](https://www.runoob.com/python3/python3-iterator-generator.html)


## 操作系统

* **进程/线程的概念和区别（头条）**
	* 进程 --> 计算机中已运行的程序，具有一定独立功能的程序关于某个数据集合上的一次运行活动，进程是系统进行资源分配和调度的一个独立单位；
	* 线程 --> 操作系统能够进行运算调度的最小单位，它被包含在进程之中，是进程中的实际运作单位。
	* 进程和线程都是一个时间段的描述，是CPU工作时间段的描述，不过是颗粒大小不同；
	* 一个程序至少有一个进程,一个进程至少有一个线程；
	* [腾讯面试题04.进程和线程的区别？](https://blog.csdn.net/mxsgoden/article/details/8821936)
	* [进程与线程的一个简单解释](http://www.ruanyifeng.com/blog/2013/04/processes_and_threads.html)
	* [线程和进程的区别是什么？](https://www.zhihu.com/question/25532384)
	* [线程 Wiki](https://zh.wikipedia.org/wiki/%E7%BA%BF%E7%A8%8B)
	* [进程 Wiki](https://zh.wikipedia.org/wiki/%E8%A1%8C%E7%A8%8B)


* **描述操作系统的启动过程（头条）**
	* 步骤 
		* BIOS
		* 主引导记录（Master boot record）
		* 硬盘启动
		* 操作系统
	* [计算机是如何启动的？](http://www.ruanyifeng.com/blog/2013/02/booting.html) 
	

* **用一门编程语言（如Java）实现一个死锁（PayPal）**
	* 禁止抢占 no preemption - 系统资源不能被强制从一个进程中退出
	* 持有和等待 hold and wait - 一个进程可以在等待时持有系统资源
	* 互斥 mutual exclusion - 只有一个进程能持有一个资源
	* 循环等待 circular waiting - 一系列进程互相持有其他进程所需要的资源
	* [死锁 Wiki](https://zh.wikipedia.org/wiki/%E6%AD%BB%E9%94%81)
	* [第18讲 | 什么情况下Java程序会产生死锁？如何定位、修复？](https://time.geekbang.org/column/article/9266)（死锁代码实例）
	* [JAVA实现的一个简单的死锁（附解释）](https://blog.csdn.net/zll793027848/article/details/8670546) 


* **如何判断内存泄漏（腾讯）**
	* 因为长生命周期持有它的引用而导致不能被回收，这就是Java中内存泄漏的发生场景；
	* [Java内存泄漏分析和解决](https://www.jianshu.com/p/54b5da7c6816)


* **什么是系统调用（爱奇艺）**
	* 指运行在用户空间的程序向操作系统内核请求需要更高权限运行的服务；
	* linux内核中设置了一组用于实现系统功能的子程序，称为系统调用。系统调用和普通库函数调用非常相似，只是系统调用由操作系统核心提供，运行于**内核态**，而普通的函数调用由函数库或用户自己提供，运行于**用户态**；
	* [系统调用 Wiki](https://zh.wikipedia.org/wiki/%E7%B3%BB%E7%BB%9F%E8%B0%83%E7%94%A8)
	* [Linux系统调用详解（实现机制分析）--linux内核剖析（六）](https://blog.csdn.net/gatieme/article/details/50779184)


## 数据结构和算法

### 排序相关

* **给定一个无符号，包含10亿个数的数组，如何取出前100大个数（头条/腾讯）**
	* 参考 --> 建立最小堆
	* [海量数据处理 - 10亿个数中找出最大的10000个数（top K问题）](https://blog.csdn.net/zyq522376829/article/details/47686867) （思路篇）


* **如何找到一个无序数组的中位数**
	* 快排 or 堆排思想
	* [找出一个无序数组的中位数](https://blog.csdn.net/oneday_789/article/details/76681764) 


* **如何给一个很大的无序数组去重（腾讯）**
	* 排序+扫描一遍去重
	* [26. 删除排序数组中的重复项](https://leetcode-cn.com/problems/remove-duplicates-from-sorted-array/)


* **Java自带的 sort() 方法是如何实现的（阿里）**
	* 双轴快速排序
	* [Collections.sort()和Arrays.sort()排序算法选择](https://blog.csdn.net/TimHeath/article/details/68930482)


* **手写快排和复杂度分析（腾讯/头条/蜻蜓FM）**
	* [快排 Wiki](https://zh.wikipedia.org/zh/%E5%BF%AB%E9%80%9F%E6%8E%92%E5%BA%8F)


* **手写堆排和复杂度分析**
	* [堆排 Wiki](https://zh.wikipedia.org/wiki/%E5%A0%86%E6%8E%92%E5%BA%8F)


### 树/链表/数组/栈/队列相关

* **二叉树的遍历**
	* 通过引入一种新的数据结构形成通用解法（Node + 是否访问标识符）
	* 用一个队列添加/删除节点
	* 用一个list存储节点
	* [二叉树的前序遍历](https://leetcode-cn.com/problems/binary-tree-preorder-traversal/)
	* [二叉树的中序遍历](https://leetcode-cn.com/problems/binary-tree-inorder-traversal/)
	* [二叉树的后序遍历](https://leetcode-cn.com/problems/binary-tree-postorder-traversal/)

	
* **根据前&中序遍历结果重建二叉树**
	* [重建二叉树](https://www.nowcoder.com/practice/8a19cbe657394eeaac2f6ea9b0f6fcf6?tpId=13&tqId=11157&rp=1&ru=/ta/coding-interviews&qru=/ta/coding-interviews/question-ranking)

	 
* **非递归实现求二叉树的深度（小红书）**
	* 引入一个队列，逐层遍历
	* [二叉树的深度（递归和非递归）---java实现](https://blog.csdn.net/snow_7/article/details/51818580)


* **红黑树描述及其复杂度分析（插入/查找）（腾讯/阿里）**
	* [红黑树 Wiki](https://zh.wikipedia.org/wiki/%E7%BA%A2%E9%BB%91%E6%A0%91) 


* **非递归从左至右打印一颗二叉树中的所有路径（拼多多）**
	* [257. 二叉树的所有路径](https://leetcode-cn.com/problems/binary-tree-paths/) 


* **反转链表（小红书/腾讯）**
	* [206. 反转链表](https://leetcode-cn.com/problems/reverse-linked-list/) 


* 如何将一棵非平衡二叉树转化成平衡二叉树（HyperS）



### 字符串

* **如何找出一个字符串中的最大不重复子串（蜻蜓FM）**
	* 暴力求解 --> 逐个遍历，找最长子串（设置一个 allUnique 函数）/ O(n^3)
	* 滑动窗口 --> 滑动窗口至到最后一个元素，每当碰到重复左指针往后走，否则右指针往后走，同时比较 / O(n)
	* [3. 无重复字符的最长子串](https://leetcode-cn.com/problems/longest-substring-without-repeating-characters/solution/wu-zhong-fu-zi-fu-de-zui-chang-zi-chuan-by-leetcod/)


### 动态规划

* **描述背包问题（HyperS）**
	* [背包问题 Wiki](https://zh.wikipedia.org/wiki/%E8%83%8C%E5%8C%85%E9%97%AE%E9%A2%98) 


### 其他

* 实现一个二叉搜索树的迭代器，包括next()和hasNext()方法（PayPal）


* **买卖股票的最佳时机（野村证券/头条）**
	* [121. 买卖股票的最佳时机](https://leetcode-cn.com/problems/best-time-to-buy-and-sell-stock/) 


* **斐波那契数列的尾递归实现（Wish）**
	* 尾递归就是把当前的运算结果（或路径）放在参数里传给下层函数，深层函数所面对的不是越来越简单的问题，而是越来越复杂的问题，因为参数里带有前面若干步的运算路径。
	* [递归与尾递归总结](https://www.cnblogs.com/Anker/archive/2013/03/04/2943498.html) 


## 数据库

### 理论

* **描述事务隔离的级别（野村证券）**
	* Serializable【可避免脏读，不可重复读，虚读】
	* Repeatable read【可避免脏读，不可重复读】
	* Read committed【可避免脏读】
	* Read uncommitted【级别最低，什么都避免不了】
	* [数据库事务隔离级别-- 脏读、幻读、不可重复读（清晰解释）](https://blog.csdn.net/jiesa/article/details/51317164)


* **delete、 drop、truncate 的区别（PayPal）**
	* drop 直接删掉表（不再需要一张表的时候，用drop）；
	* truncate 删除的是表中的数据，再插入数据时自增长的数据id又重新从1开始（保留表而删除所有数据的时候用truncate）；
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

	 
## 计算机网络

* **介绍 OSI 七层模型**
	* [OSI七层模型详解](https://blog.csdn.net/yaopeng_2005/article/details/7064869) （上课很重要，但目前还没面到过）
	* [干货：计算机网络知识总结.md](https://github.com/Snailclimb/JavaGuide/blob/master/docs/network/%E5%B9%B2%E8%B4%A7%EF%BC%9A%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%9F%A5%E8%AF%86%E6%80%BB%E7%BB%93.md#%E4%B8%80%E8%AE%A1%E7%AE%97%E6%9C%BA%E6%A6%82%E8%BF%B0)（逐层术语解释）

	
* **描述三次握手四次挥手（阿里）**
	* 三次握手
		* 发送端 --> SYN / 接收端 --> [SYN/ACK] / 发送端 --> ACK
			* SYN 是 TCP/IP 建立连接时使用的握手信号
		* 需要三次握手原因：双方确认自己与对方的发送与接收是正常的
		* 接收端回传SYN --> 告诉发送端我接收到的信息确实就是你所发送的信号
	* 四次挥手
		* 发送端 --> FIN (客户端进入FIN-WAIT-1（终止等待1）状态) / 接收端 --> ACK (客户端收到服务器的确认请求后，此时，客户端就进入FIN-WAIT-2（终止等待2）状态) / 接收端 --> FIN / 发送端 --> ACK
	* [TCP的三次握手与四次挥手（详解+动图）](https://blog.csdn.net/qzcsu/article/details/72861891)

	
* **用Socket描述TCP的三次握手（腾讯）** *（TODO）*
	* [Socket过程详细解释（包括三次握手建立连接，四次握手断开连接）](https://blog.csdn.net/u013782203/article/details/51767763)（C++实现，未看）


* **网络间的进程如何表示（腾讯）** *（TODO）*
	* [网络中进程之间如何通信](https://blog.csdn.net/bajiudongfeng/article/details/51568874) 

	
* **TCP和UDP的特点和区别**
	* TCP --> 面向连接 / UDP --> 无连接（发送数据前不需要建立连接）
	* TCP 提供可靠的服务（数据传输）/ UDP 无法保证
	* TCP --> 字节流 / UDP --> 数据报文段
	* [TCP和UDP的区别](https://zhuanlan.zhihu.com/p/24860273)
	* [常见面试题整理--计算机网络篇（每位开发者必备）](https://zhuanlan.zhihu.com/p/24001696)


* **从客户端输入一个URL，该请求是如何传到服务端的（爱奇艺）**
	* DNS解析
		* 递归查询 --> 该模式下DNS 服务器接收到客户机请求，必须使用一个准确的查询结果回复客户机。
		* 迭代查询 --> DNS 服务器并不直接回复查询结果，而是告诉客户机另一台DNS 服务器地址，客户机再向这台DNS 服务器提交请求，依次循环直到返回查询的结果
	* 建立TCP连接
	* 发送HTTP请求
	* 服务器处理请求并返回HTTP报文
	* 浏览器解析并渲染页面
	* 连接结束
	* [从输入URL到页面加载发生了什么](https://segmentfault.com/a/1190000006879700)（依次逐步解释）
 	* [在浏览器地址栏输入一个URL后回车，背后会进行哪些技术步骤？](https://www.zhihu.com/question/34873227)（更具体的解释）
 	* [DNS递归查询和迭代查询的区别](https://blog.csdn.net/wuchuanpingstone/article/details/6720723)


* **描述HTTPS的加密过程（头条）** *（TODO）*
	* [HTTPS加密过程和TLS证书验证](https://juejin.im/post/5a4f4884518825732b19a3ce)


* **HTTP代理如何实现（阿里）** *（TODO）*
	* [如何实现一个HTTP/HTTPS代理客户端 ](https://github.com/fwon/blog/issues/38)


## Linux相关

### 常见Linux指令 *（TODO）*

* top，load 指令，free 中 cached和buffers的区别（阿里）
	* 
* 找出某目录下文件中带电子邮箱的文件（爱奇艺）
	* 


## 编程之美

### 设计模式

* **简述设计模式**
	* 创建型 / 结构型 / 行为型
	* [第14讲 | 谈谈你知道的设计模式？](https://time.geekbang.org/column/article/8624)

	 
* **实现一个线程安全的单例模式**
	* 懒汉模式 --> Lazy初始化
	* 饿汉模式 --> 在方法调用前，实例就已经创建好了
	* 全部 sychronized 锁住 --> 可以保证线程安全，但销效率低
	* “双重检查锁”机制 （面试答这个吧）
		* volatile 来保证其线程间的可见性
		* 同步代码块中使用二次检查，以保证其不被重复实例化
	* 枚举enum和静态代码块的特性相似，在使用枚举时，构造方法会被自动调用，利用这一特性也可以实现单例（面试可稍微提及）
	* [高并发下线程安全的单例模式（最全最经典）](https://blog.csdn.net/cselmu9/article/details/51366946) （单例的N种实现）
	* [单例模式](https://www.runoob.com/design-pattern/singleton-pattern.html)（详尽介绍）


* **设计一个方案，提供不同算法调用接口（参数即为需要调用的方法名）（设计模式实际应用）（PayPal）**
	* 这题感觉非常开放，我当时答了用 适配器模式，似乎面试官并不是特别满意
	* 适配器模式 应该是可以的
	* 工厂模式( *"定义一个创建对象的接口，让其子类自己决定实例化哪一个工厂类，工厂模式使其创建过程延迟到子类进行。"* ) 应该也可以 --> 传入方法参数，实例化具体对象
	* [两道设计模式的面试题](https://www.cnblogs.com/Binhua-Liu/archive/2010/12/23/1914935.html)
	* [工厂模式](https://www.runoob.com/design-pattern/factory-pattern.html)


## 其他

* **git rebase 和 git merge 有什么区别（小红书/野村证券/PayPal）**
	* [git rebase 和 git merge 的区别](https://www.jianshu.com/p/f23f72251abc)*（TODO）*
 

* **git fetch 和 git pull 有什么区别（PayPal）**
	* [详解git fetch与git pull的区别](https://blog.csdn.net/riddle1981/article/details/74938111) *（TODO）*


* 描述 git 中的 cherry-pick 指令（小红书）


* **如何设计一个秒杀系统（小红书）** *（TODO）*
	* [Java开发面试：高并发秒杀系统如何设计与优化](https://blog.csdn.net/CSDN_Terence/article/details/77744042)
	* [如何设计一个秒杀系统](https://blog.csdn.net/suifeng3051/article/details/52607544)