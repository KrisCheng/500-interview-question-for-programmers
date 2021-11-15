# 500-interview-question-for-programmers

## 概述

本 `Repository` 用于记录个人平时面试和学习时碰到的一些有价值的问题，所有问题均为我**真实碰到过且思考过**（大部分附具体面试公司），一律采用问答形式，答案为我个人的理解和整理，不一定正确（标记 *`TODO`* 为还没来得及弄或自己也没搞懂 Orz...），欢迎指正（可以提 `Issues`，亦可邮件交流 [*kris.dacpc@gmail.com*](mailto:kris.dacpc@gmail.com)）。

侧重点是个人对某些问题的总结，并基于此形成个人专业的 `Knowledge Base` （提供配套思维导图），`materials`目录为个人的一些总结，希望以此来保持个人知识体系的扎实性。

供所有正在找工作的小伙伴们参考，如果觉得有帮助，请 `Star` ，善用 `Ctrl` + `F` :)。

## 算法和设计


* 详见 [科学刷题指北](科学刷题指北.md).



## Java

### 基础

* **字符串相关问题**
	* StringBuffer --> 线程安全 （使用 synchronized 关键字实现）
	* StringBuilder --> 非线程安全
	* 底层实现均为**可修改数组**（char, JDK 9 以后是byte数组）
	* [第5讲 | String、StringBuffer、StringBuilder有什么区别？](https://time.geekbang.org/column/article/7349)


* **什么是序列化（Serialization）和反序列化（小红书）**
	* 序列化 --> 把**对象**转换为**字节序列**的过程称为对象的序列化
	* 反序列化 --> 把字节序列恢复为对象的过程称为对象的反序列化
	* [Java 序列化](https://www.runoob.com/java/java-serialization.html)（介绍）
	* [Java对象的序列化（Serialization）和反序列化详解](https://blog.csdn.net/yaomingyang/article/details/79321939)（实例）
	* [二叉树的序列化与反序列化](https://leetcode-cn.com/problems/serialize-and-deserialize-binary-tree/) 

* **Java中父类和子类初始化顺序（小红书）**
	* 优先级排序
		* 1. 父类中静态成员变量 **和** 静态代码块
		* 2. 子类中静态成员变量 **和** 静态代码块
		* 3. 父类中普通成员变量 **和** 代码块，父类的构造函数
		* 4. 子类中普通成员变量 **和** 代码块，子类的构造函数
		* (其中 “和” 字两端按照代码先后顺序执行)
	* [java中父类和子类初始化顺序](https://blog.csdn.net/yuxin6866/article/details/53107578) 


* **什么是反射 && 反射的具体应用**
	* Java反射机制是在**运行状态中**，对于任意一个类，都能够知道这个类的所有属性和方法；对于任意一个对象，都能够调用它的任意一个方法和属性。这种 **动态获取的信息以及动态调用对象的方法的功能** 称为Java语言的反射机制
	* 应用
		* 框架设计的灵魂 --> 如：Spring 通过 XML 配置模式装载 Bean 的过程
		* 使用JDBC连接数据库时使用 Class.forName() 通过反射加载数据库的驱动程序
	* [Java基础之—反射（非常重要）](https://blog.csdn.net/sinat_38259539/article/details/71799078)（反射实例 *`TODO`*）
	* [What is the difference between “Class.forName()” and “Class.forName().newInstance()”?](https://stackoverflow.com/questions/2092659/what-is-the-difference-between-class-forname-and-class-forname-newinstanc)（Class.forName(String) returns the Class object associated with the class or interface with the given string name && newInstance() creates a new instance of the class）
	
* **Java提供了哪些IO方式（或者描述IO）（拼多多/字节跳动）** *`TODO`*
	* 同步 / 异步 --> 关注的是消息通信机制（区别最大在于异步的话调用者不需要等待处理结果）
	* 阻塞 / 非阻塞 --> 关注的是程序在等待调用结果（消息，返回值）时的状态
	* BIO / NIO（概念描述，网易）
	* 描述Spring中的IO方式（字节跳动）
	* [Java NIO Tutorial](http://tutorials.jenkov.com/java-nio/index.html) （教程  *`TODO`* ）
	* [怎样理解阻塞非阻塞与同步异步的区别？](https://www.zhihu.com/question/19732473) 
	* [第11讲 | Java提供了哪些IO方式？ NIO如何实现多路复用？](https://time.geekbang.org/column/article/8369)（思想 + 实例 *`TODO`*）
	* [Lesson: Basic I/O](https://docs.oracle.com/javase/tutorial/essential/io/index.html)（官方 IO Docs *`TODO`*）
	* [Java NIO浅析](https://zhuanlan.zhihu.com/p/23488863)（技术blog + 实例 *`TODO`*）
	* select 和 epoll 的区别（字节跳动） *`TODO`* 
	  * [select和epoll区别](https://www.jianshu.com/p/430141f95ddb)


* **描述 Java8 的新特性（星环）**  *`TODO`*
	* lambda 表达式，以及使用 lambda 表达式的场景
	* Stream


* **关键字** 
	* ***static***
		* the keyword static indicates that the particular member belongs to a type itself, rather than to an instance of that type
		* 在没有创建任何对象的前提下，仅仅通过类本身来调用 static 方法。这实际上正是 static 方法的主要用途
		* [A Guide to the Static Keyword in Java](https://www.baeldung.com/java-static)
	* ***final*** 
	* ***finally***
	  * try-catch-finally 中包含 return 的情况分析（字节跳动）
	    * "finally块中的内容会先于try中的return语句执行，如果finally语句块中也有return语句的话，那么直接从finally中返回了"
	  * “不要在 finally 代码块中使用 return 语句”（ [《码出高效》](https://book.douban.com/subject/30333948/)  5.2）




### 集合框架

* **ArrayList和LinkedList的区别（源码级别）（字节跳动）** 
* **描述 HashMap 的底层实现（远景智能/字节跳动/百度）**
	* 解决哈希冲突
		* JDK < 1.8 --> 数组+链表
		* JDK >= 1.8 --> 数组+链表+红黑树，链表长度大于阈值（默认为8）时，将链表转化为红黑树，以减少搜索时间
	* 源码阅读  *`TODO`*
		* get() / put() / resize()
		* capacity / load factor (负载因子)（**这两个参数具体是什么，有什么用？不同设置有什么差异（星环/字节跳动）** ）
			* “the initial capacity is simply the capacity at the time the hash table is created”（bucket数目）
			* ”The load factor is a measure of how full the hash table is allowed to get before its capacity is automatically increased“（bucket填满程度的最大比例）
			* “When the number of entries in the hash table exceeds the product of the load factor and the current capacity, the hash table is rehashed (that is, internal data structures are rebuilt) so that the hash table has approximately twice the number of buckets”
			* “如果内存空间很多而又对时间效率要求很高，可以降低负载因子load factor的值；相反，如果内存空间紧张而对时间效率要求不高，可以增加负载因子loadFactor的值，这个值可以大于1”
	*  [Java HashMap工作原理及实现](https://yikun.github.io/2015/04/01/Java-HashMap%E5%B7%A5%E4%BD%9C%E5%8E%9F%E7%90%86%E5%8F%8A%E5%AE%9E%E7%8E%B0/) （基本参考）
	*  [Java 8系列之重新认识HashMap](https://tech.meituan.com/2016/06/24/java-hashmap.html) （主要参考）
	* [Class HashMap<K,V>](https://docs.oracle.com/javase/8/docs/api/java/util/HashMap.html) （Java 8 Docs）
	* [Java源码分析：关于 HashMap 1.8 的重大更新](https://blog.csdn.net/carson_ho/article/details/79373134)（1.7 vs 1.8 详细比较）


* **ConcurrentHashMap 实现原理，或者说它是怎么保证线程安全的（星环/字节跳动/阿里）** *`TODO`*
	* HashMap `resize()` 在多线程环境下可能形成环形链表，从而导致死循环
	* JDK1.7 --> 分段锁（ Segment 对象，继承自 ReentrantLock ）+ HashEntry
	* JDK1.8 --> CAS + synchronized 保证并发安全性
	* [HashMap? ConcurrentHashMap? 相信看完这篇没人能难住你！](https://crossoverjie.top/2018/07/23/java-senior/ConcurrentHashMap/)（面试大全  *`TODO`*）
	* [深入浅出ConcurrentHashMap1.8](https://www.jianshu.com/p/c0642afe03e0)（1.8版本的详细解释）
	* [老生常谈，HashMap的死循环](https://juejin.im/post/5a66a08d5188253dc3321da0)（具体分析 非线程安全带来的无限循环占用 CPU100% 问题）


* **HashMap 和 TreeMap 的区别和应用场景（PayPal/依图）**
	* HashMap 通过 hashcode 对其内容进行快速查找，而 TreeMap 中所有的元素都保持着某种固定的顺序，需要得到一个有序的结果你就应该使用 TreeMap，HashMap中元素的排列顺序是不固定的
	* HashMap 允许使用 null 值和 null 键，而 TreeMap 不可以
	* 源码实现
		* HashMap --> HashMap实际上是一个“链表散列”的数据结构，即数组和链表的结合体 / 如果追加节点后，链表数量 >= 8，则转化为红黑树
		* TreeMap --> 红黑树
	* HashMap 非线程安全 && TreeMap 非线程安全
	* [HashMap和TreeMap区别详解以及底层实现](https://blog.csdn.net/xlgen157387/article/details/47907721)（概念+比较）
	* [第9讲 | 对比Hashtable、HashMap、TreeMap有什么不同？ ](https://time.geekbang.org/column/article/8053) （概念+源码分析） 

* **HashSet 如何判断重复元素（小红书）**
  * 首先会调用 Object 的 `hashCode()` 方法判 hashCode 是否已经存在，如不存在则直接插入元素
  * 如果已存在则调用 Object 对象的 `equals()` 方法判断是否返回true， 如果为true则说明元素已经存在，如为false则插入元素
  * Java对象的 `equals()` 方法和 `hashCode()`  方法规定：
    * 相等（相同）的对象必须具有相等的哈希码（或者散列码）
    * 如果两个对象的hashCode相同，它们并不一定相同
  * [HashSet重复元素判断](https://itfafa.iteye.com/blog/1698690) 
  * [Java提高篇——equals()与hashCode()方法详解](https://www.cnblogs.com/Qian123/p/5703507.html) 



### JVM相关

* **描述 Java 中的类加载过程（阿里/星环）**

  * 主要有 加载（Loading） --> 链接（Linking） --> 初始化（Initializing）三个步骤
  * 加载
    * 将字节码数据从不同的数据源读取到 JVM 中，并映射为 JVM 认可的数据结构（Class对象），用户可以自定义类加载器（用户参与），实现类加载过程
  * 链接 --> 把原始的类定义信息平滑地转化到JVM运行的过程中，细分为：
    * 验证（Verification）
      * 确保Class文件的字节流中包含的信息符合JVM的全部约束要求，保证这些信息被当做代码后不会危害虚拟机自身的安全
    * 准备（Preparation）
      * 正式为类变量分配内存并设置类变量初始值的阶段
    * 解析（Resolution）
      * 虚拟机将常量池内的符号引用替换为直接引用的过程（直接引用是可以直接指向目标的指针、相对偏移量或者是一个能间接定位到目标的句柄）
  * 初始化（Initializing）
    * 真正执行类中定义的 Java 程序代码(字节码)，初始化阶段就是执行类构造器  <clinit>() 方法（Javac编译器的自动生成物）的过程。 （《深入理解Java虚拟机》第三版 P277）
  * 双亲委派模型（Parents Delegation Model，宜译作“溯源委派加载模型”（[《码出高效》](https://book.douban.com/subject/30333948/) P119））
    * 如果一个类加载器收到了类加载的请求，它首先不会自己去尝试加载这个类，而是把这个请求委派给父类加载器去完成，每一个层次的类加载都是如此，因此所有的加载请求最终都应该传送到最顶层的启动类加载器中，只有当父加载器反馈自己无法完成这个加载请求时，子加载器才会尝试自己去完成加载
    * 好处 --> Java中的类随着它的加载器一起具备了一种带有优先级的层次关系，避免类的重复加载
    * 实现 
      * 1.检查请求加载的类型是否已经被加载过，没有则调用父加载器的 loadClass() 方法；
      * 2.若父加载器为空则默认使用启动类加载器作为附加载器；
      * 3.加入父类加载器加载失败，抛出ClassNotFoundException，才调用自己的 findClass() 方法尝试进行加载
    * 为什么要用双亲委派模型呢（阿里）
  * [类加载过程](https://github.com/Snailclimb/JavaGuide/blob/master/docs/java/jvm/类加载过程.md)（基本过程解释）

  * [第23讲 | 请介绍类加载过程，什么是双亲委派模型？](https://time.geekbang.org/column/article/9946)（简介 + 各步骤实例）
  * [Java Virtual Machine Specification Chapter 5. Loading, Linking, and Initializing](https://docs.oracle.com/javase/specs/jvms/se8/html/jvms-5.html)（官方JVM虚拟机规范 Docs *`TODO`* ）
  * 《深入理解Java虚拟机：JVM高级特性与最佳实践》第7章 -- 虚拟机类加载机制

* **如何自定义类加载器** 

  * [JVM——自定义类加载器](https://blog.csdn.net/SEU_Calvin/article/details/52315125) 

* **描述 Java 中的类加载机制（星环）**

  * Java虚拟机把描述类的数据从Class文件加载到内存，并对数据进行校验、转换解析和初始化，最终形成可以被虚拟机直接使用的Java类型，这个过程被称作虚拟机的类加载机制（《深入理解Java虚拟机》第三版 P262）

* **描述Java内存模型（阿里/美团/网易）**  *`TODO`* 
	
	* JVM内存区域划分 
		* 程序计数器（PC, Program Counter Register） --> 它的作用可以看做是当前线程所执行的字节码的行号指示器
		* 虚拟机栈（Virtual Machine Stack） --> 保存一个个**栈帧（Stack Frame）**，对应着一次次的 Java **方法调用**
		* 本地方法栈（Native Method Stack） --> 和虚拟机栈类似，区别为虚拟机栈为虚拟机执行Java方法（也就是字节码）服务，而本地方法栈为虚拟机使用到的Native方法服务
		
			⬆️（线程私有）--- （线程共享） ⬇️
		
		* 堆（Heap） --> 虚拟机管理的内存中最大的一块，所有线程共享的内存区域，几乎所有的 **对象实例** 都在这里分配内存
		* 方法区（Method Area） --> 所有线程共享的一块内存区域，用于存储所谓的元（Meta）数据，如类结构信息，以及对应的运行时常量池、字段、方法代码等
		* 运行时常量池（Run-Time Constant Pool） --> 属于方法区的一部分，存放各种常量信息
		
	* [第25讲 | 谈谈JVM内存区域的划分，哪些区域可能发生OutOfMemoryError?](https://time.geekbang.org/column/article/10192)
	
	* [Java 内存区域详解](https://github.com/Snailclimb/JavaGuide/blob/master/docs/java/jvm/Java%E5%86%85%E5%AD%98%E5%8C%BA%E5%9F%9F.md)
	
	* [The Structure of the Java Virtual Machine](https://docs.oracle.com/javase/specs/jvms/se9/html/jvms-2.html)（官方 Docs *`TODO`* ）
	
* **描述GC**

  * 对象存活判断
    * 引用计数（Python 的 GC），无法解决对象相互循环引用的问题，Java中没有使用（Python GC有应用）
    * 可达性分析（GC Roots --> 虚拟机栈和本地方法栈中正在引用的对象、静态属性引用的对象和常量）
  * 垃圾收集算法
    * 标记-清除算法（Mark-Sweep） --> 内存碎片化问题
    * 复制算法（Copying） --> 将内存分为大小相同的两块，每次使用其中的一块。每次将活着的对象复制到 to 区域，拷贝过程中将对象顺序放置，避免内存碎片化
    * 标记-整理算法（Mark-Compact） --> 类似于标记-清除，但为了避免内存碎片化，**在清理过程中移动对象，以确保移动后的对象占用连续的内存空间**
    * 分代收集算法 --> 根据对象存活周期的不同将内存分为几块 （eg: 新生代/老生代）
  * 频繁的 Full GC 怎么排查（阿里）
  * 《深入理解Java虚拟机》第三版 第3章
  * [jvm系列(三):GC算法 垃圾收集器](https://mp.weixin.qq.com/s?__biz=MzI4NDY5Mjc1Mg==&mid=2247483952&idx=1&sn=ea12792a9b7c67baddfaf425d8272d33&chksm=ebf6da4fdc815359869107a4acd15538b3596ba006b4005b216688b69372650dbd18c0184643&scene=21#wechat_redirect)
  * [JVM 垃圾回收](https://github.com/Snailclimb/JavaGuide/blob/master/docs/java/jvm/JVM%E5%9E%83%E5%9C%BE%E5%9B%9E%E6%94%B6.md) 


* **描述JVM中常见的垃圾回收器，如CMS，以及JVM调优思路（美团）** *`TODO`* 
	* [一文了解JVM全部垃圾回收器，从Serial到ZGC](https://juejin.im/post/5bade237e51d450ea401fd71)
	* [第27讲 | Java常见的垃圾收集器有哪些？](https://time.geekbang.org/column/article/10513)
	* [《码出高效》](https://book.douban.com/subject/30333948/)  P134~P138


* **Java中什么时候会发生OOM（华为）** 
  
  * 除了程序计数器，虚拟机内存的其他几个运行时区域都哟与发生OOM异常的可能
  * 《深入理解Java虚拟机》第三版 2.4
  * [Java内存溢出(OOM)异常完全指南](https://www.jianshu.com/p/2fdee831ed03) 
* **NoClassDefFoundError和ClassNotFoundException的场景和解决办法（星环）**



### Java并发编程 *`TODO`*

* **描述Java下的并发编程（阿里）**
	* Java中实现并发编程的手段 --> 多线程
	* 线程的生命周期（新建 / 就绪 / 运行 / 阻塞 / 死亡）（网易）
	  * 线程阻塞和等待的区别（网易）
	  * [啃碎并发（二）：Java线程的生命周期](https://juejin.cn/post/6844903558433734669) 
	  * [Difference between WAIT and BLOCKED thread states](https://stackoverflow.com/questions/15680422/difference-between-wait-and-blocked-thread-states) 
	* 创建线程的方法
		* Runnable 接口
		* 继承 Thread
		* 通过 Callable 和 Future 创建线程
	* [Java 多线程编程](https://www.runoob.com/java/java-multithreading.html) （生命周期）


* **什么是线程安全**
	* a class is thread safe when it continues to behave correctly when accessed from multiple threads
	* 指某个函数、函数库在多线程环境中被调用时，能够正确地处理多个线程之间的共享变量，使程序功能正确完成
	* [线程安全 Wiki](https://zh.wikipedia.org/wiki/%E7%BA%BF%E7%A8%8B%E5%AE%89%E5%85%A8)
	
* **synchronized 和 ReentrantLock（Lock） 比较（字节跳动）**
	* synchronized 锁住的是括号里的对象，而不是代码
	* 描述 synchronized 的底层实现（爱奇艺） *`TODO`*
	* 可重入 --> 当一个线程试图获取一个它已经获取的锁时，这个获取动作就自动成功（自己可以再次获取自己的内部锁）
	* ReentrantLock 源码阅读 *`TODO`*
		* 描述 AQS（AbstractQueuedSynchronizer）的作用（网易）（另一个问法为 ReentrantLock里提供了一个很好的工具，你知道这个工具是什么吗？（星环））
	* [Java线程同步：synchronized锁住的是代码还是对象](https://blog.csdn.net/xiao__gui/article/details/8188833) 
	* [第15讲 | synchronized和ReentrantLock有什么区别呢？](https://time.geekbang.org/column/article/8799) 


* **介绍 volatile 关键字（阿里/网易）**
	* 只能用于变量（is used to mark a Java variable as "being stored in main memory"）
	* 保证变量的可见性（指示 JVM，这个变量是不稳定的，每次使用它都到主存中进行读取） && 防止指令重排序
	* 对一个 volatile 变量的写操作， Happens-Before 后续对这个 volatile 变量的读操作
	* [Java Volatile Keyword](http://tutorials.jenkov.com/java-concurrency/volatile.html) 

* **Java中如何使用线程池，以及线程池有哪些重要的参数（阿里/字节跳动） / 线程池有哪些类型（百度）**
	* 生产者 - 消费者 模式的一种实现
	* 线程池的好处
		* 降低资源消耗 / 提高响应速度 / 提高线程的可管理性
	* 使用方法
		* ThreadPoolExecutor类
			* 线程池中的每一个线程被封装成一个 Worker 对象，ThreadPool 维护的其实就是一组 Worker 对象
			* 一些主要参数
				* corePoolSize --> 核心线程数
				* maximumPoolSize --> 最大能创建的线程数（可以理解为当任务量突然过大时的一种补救措施）
				* workQueue --> 工作队列，为 BlockingQueue，用于存储等待执行的任务
	* IO密集型和计算密集型任务如何配置线程池参数（字节跳动）
	  * [Java线程池实现原理及其在美团业务中的实践](https://tech.meituan.com/2020/04/02/java-pooling-pratice-in-meituan.html) 
	* [《码出高效》](https://book.douban.com/subject/30333948/)  7.4.2（线程池源码详解，关键方法逐行解释）
	* [22 | Executor与线程池：如何创建正确的线程池？](https://time.geekbang.org/column/article/90771)（基本介绍和主要参数）
	* [深入理解 Java 线程池：ThreadPoolExecutor](https://juejin.im/entry/58fada5d570c350058d3aaad)（ThreadPoolExecutor 源码和关键类分析）
	* [Java并发编程：线程池的使用](https://www.cnblogs.com/dolphin0520/p/3932921.html)（ThreadPoolExecutor 源码 和 基本用法）
	* [第21讲 | Java并发类库提供的线程池有哪几种？ 分别有什么特点？](https://time.geekbang.org/column/article/9712)（介绍 Executor 框架和从设计角度介绍ThreadPoolExecutor类）


* **乐观锁与悲观锁的概念，常见实现（阿里）**
	* 乐观锁适用于**多读**的应用类型，这样可以提高吞吐量 / 悲观锁适合于**多写**
	* 乐观锁常见实现 --> 版本号机制 / CAS 算法
		* CAS 算法概念 / 缺点
			* 自旋 --> 循环尝试
			* ABA 问题
	* [何谓悲观锁与乐观锁](https://github.com/Snailclimb/JavaGuide/blob/master/docs/essential-content-for-interview/%E9%9D%A2%E8%AF%95%E5%BF%85%E5%A4%87%E4%B9%8B%E4%B9%90%E8%A7%82%E9%94%81%E4%B8%8E%E6%82%B2%E8%A7%82%E9%94%81.md) （基本介绍）


* **join() 方法有什么用**
	* Thread.join() 把指定的线程加入到当前线程，可以将两个交替执行的线程合并为顺序执行的线程。比如在线程B中调用了线程A的join()方法，直到线程A执行完毕后，才会继续执行线程B
	* [Java多线程中join方法的理解](https://uule.iteye.com/blog/1101994)
	* [简谈Java的join()方法](https://www.cnblogs.com/techyc/p/3286678.html)  


* **描述 Atomic 类的底层实现（美团）** *`TODO`*


* **描述ThreadLocal 的实现（美团），什么情况会发生OOM（星环）** *`TODO`*

  * "它通常用于同一个线程内，跨类、跨方法传递数据"
  * [Java ThreadLocal](http://tutorials.jenkov.com/java-concurrency/threadlocal.html) 
  * [《码出高效》](https://book.douban.com/subject/30333948/)  7.5
* **synchronized和Lock的比较（使用/性能/效率），以及为什么会有这种差别（字节跳动）** 


* **Java并发学习资源** 
  * [Java并发编程学习路线](https://zhuanlan.zhihu.com/p/25577863)（学习思路篇）
  * [Java Concurrency in Practice](https://book.douban.com/subject/1888733/)（*`TODO`*）
  * [Java并发编程实战](https://time.geekbang.org/column/intro/159) （极客时间课程）
  * [《码出高效》](https://book.douban.com/subject/30333948/)  7（几个并发工具类源码阅读）



## Python

### 基础


* **Python如何实现真正的多线程（阿里/腾讯）**  *`TODO`*
  * [Python 多线程](https://www.runoob.com/python/python-multithreading.html) 
* **给一段Python代码，有哪些优化思路和策略（阿里）**   *`TODO`* 


* **如何写一个程序计算一段Python代码的耗时（腾讯） **  *`TODO`* 


* **Python爬虫中存在环引用该如何处理（阿里）** *`TODO`* 



### Pythonic


* **实现一个lambda表达式（字节跳动）**
  * 匿名函数，个人理解为一种语法糖
  * [Lambda 表达式有何用处？如何使用？](https://www.zhihu.com/question/20125256)
* **用map/reduce实现数组求和（PayPal）**

  * map --> 将传入函数依次作用于序列中的每个元素，并把结果作为新的Iterator返回;
  * reduce --> 累积计算, 求和 ```reduce(lambda x, y : x + y, [1,2,3,4,5])```.
  * [map/reduce](https://www.liaoxuefeng.com/wiki/1016959663602400/1017329367486080)
* **描述Python的迭代器和生成器（DaoCloud）** *`TODO`* 
  * [Python3 迭代器与生成器](https://www.runoob.com/python3/python3-iterator-generator.html) 



### Async IO

* [python_asyncio_learning](https://github.com/KrisCheng/python_asyncio_learning)



### Package Management




## 操作系统

* **进程/线程的概念和区别（字节跳动/拼多多）** 
  * 进程 --> 计算机中运行中的程序，具有一定独立功能的程序关于某个数据集合上的一次运行活动，进程是系统进行资源分配和调度的一个独立单位
  * 线程 --> 操作系统能够进行运算调度的最小单位，它被包含在进程之中，是进程中的实际运作单位
  * 进程和线程都是一个CPU工作时间段的描述，不过是颗粒大小不同。一个程序至少有一个进程，一个进程至少有一个线程
  * 类比 --> 进程=火车，线程=车厢
  * [腾讯面试题04.进程和线程的区别？](https://blog.csdn.net/mxsgoden/article/details/8821936) 
  * [线程和进程的区别是什么？](https://www.zhihu.com/question/25532384) 
  * [线程 Wiki](https://zh.wikipedia.org/wiki/%E7%BA%BF%E7%A8%8B) / [进程 Wiki](https://zh.wikipedia.org/wiki/%E8%A1%8C%E7%A8%8B)
  * [进程与线程的一个简单解释](http://www.ruanyifeng.com/blog/2013/04/processes_and_threads.html) （科普，类比：进程 -- 车间 / 线程 -- 车间里的工人）


* **线程同步（通信）的方式（字节跳动）**   *`TODO`* 
  
  * 同步 -- 协同步调，按预定的先后次序进行运行

    * wait() -- It tells the calling thread to give up the lock and go to sleep until some other thread enters the same monitor and calls notify().（线程自动释放其占有的对象锁，并等待notify）
    * notify() -- It wakes up one single thread that called wait() on the same object. It should be noted that calling notify() does not actually give up a lock on a resource.（唤醒一个正在wait当前对象锁的线程，并让它拿到对象锁）
    * notifyAll() -- It wakes up all the threads that called wait() on the same object.（唤醒所有正在wait当前对象锁的线程）
  * [Inter-thread communication in Java](https://www.javatpoint.com/inter-thread-communication-example) 
  * [JAVA线程间通信的几种方式](https://blog.csdn.net/u011514810/article/details/77131296) （一个实例）
* **进程间通信的方式（依图）** 
	* 进程间通信 --> 在不同进程之间传播或交换信息
		* 管道（数据只能单向流动）
		* 系统IPC（InterProcess Communication）（包括消息队列，信号量，共享存储）
		* Socket（可用于不同机器间的进程通信）
	* [进程间的几种通信方式](https://blog.csdn.net/yufaw/article/details/7409596)
	* [进程间8种通信方式详解](https://blog.csdn.net/violet_echo_0908/article/details/51201278) 
* **Java中start() 和 run() 方法的区别（字节跳动）** 

  * start() -- Creates a new thread and the run() method is executed on the newly created thread. (Can’t be invoked more than one time otherwise throws *java.lang.IllegalStateException*)
  * run() -- No new thread is created and the run() method is executed on the calling thread itself. (Multiple invocation is possible)
  * [Difference between Thread.start() and Thread.run() in Java](https://www.geeksforgeeks.org/difference-between-thread-start-and-thread-run-in-java/) 
* **sleep()和wait()的区别，应用场景（字节跳动）** 

  * [Difference between Wait and Sleep, Yield in Java](https://javarevisited.blogspot.com/2011/12/difference-between-wait-sleep-yield.html#axzz6jzKp3QZM) 


* **描述操作系统的启动过程（字节跳动）**
	* 步骤 
		* BIOS（Basic Input / Output System）
		* 主引导记录（Master boot record）
		* 硬盘启动
		* 操作系统
	* [计算机是如何启动的？](http://www.ruanyifeng.com/blog/2013/02/booting.html) 
	
* **用一门编程语言（如Java）实现一个死锁（PayPal）**
	* 死锁产生的条件
		* 禁止抢占 no preemption --> 系统资源不能被强制从一个进程中退出
		* 持有和等待 hold and wait --> 一个进程可以在等待时持有系统资源
		* 互斥 mutual exclusion --> 只有一个进程能持有一个资源
		* 循环等待 circular waiting --> 一系列进程互相持有其他进程所需要的资源
	* [死锁 Wiki](https://zh.wikipedia.org/wiki/%E6%AD%BB%E9%94%81) 
	* [第18讲 | 什么情况下Java程序会产生死锁？如何定位、修复？](https://time.geekbang.org/column/article/9266)（死锁代码实例）
	* [JAVA实现的一个简单的死锁（附解释）](https://blog.csdn.net/zll793027848/article/details/8670546) 


* **如何判断内存泄漏（腾讯）**
	* 因为长生命周期持有它的引用而导致不能被回收，这就是Java中内存泄漏的发生场景
	* [Java内存泄漏分析和解决](https://www.jianshu.com/p/54b5da7c6816)


* **什么是系统调用（爱奇艺）**
	* 指运行在用户空间的程序向操作系统内核请求需要更高权限运行的服务
	* linux内核中设置了一组用于实现系统功能的子程序，称为系统调用。系统调用和普通库函数调用非常相似，只是系统调用由操作系统核心提供，运行于**内核态**，而普通的函数调用由函数库或用户自己提供，运行于**用户态**
	* [系统调用 Wiki](https://zh.wikipedia.org/wiki/%E7%B3%BB%E7%BB%9F%E8%B0%83%E7%94%A8)
	* [Linux系统调用详解（实现机制分析）--linux内核剖析（六）](https://blog.csdn.net/gatieme/article/details/50779184)
	* [用户态和内核态的区别](https://blog.csdn.net/youngyoungla/article/details/53106671) 
* **kill掉一个进程（从指令输入开始），操作系统做了什么事情（字节跳动）**

  * PCB
* **分页&&分段存储（字节跳动）** 



## 数据库

### 数据库理论

* **描述事务的隔离级别（野村证券/远景智能/网易）**
	* Serializable（序列化） --> 可避免脏读，不可重复读，幻读
	* Repeatable read（可重复读） --> 可避免脏读，不可重复读，但可能出现幻读 
	* Read committed（已提交读） --> 可避免脏读，但是可能会造成不可重复读
	* Read uncommitted（未提交读） --> 级别最低，什么都避免不了（事务可以看到其他事务“尚未提交”的修改）
	* 脏读 --> 当一个事务允许读取另外一个事务修改但未提交的数据时，就可能发生 脏读
	* 不可重复度 --> 在一次事务中，当一行数据获取两遍得到不同的结果表示发生了 不可重复读
	* 幻读 --> 在事务执行过程中，当两个完全相同的查询语句执行得到不同的结果集。这种现象称为 幻读
	* [MySQL 事务隔离级别和锁](https://developer.ibm.com/zh/technologies/databases/articles/os-mysql-transaction-isolation-levels-and-locks/) 
	* [ACID Wiki](https://zh.wikipedia.org/wiki/ACID)
	* [事务隔离 Wiki](https://zh.wikipedia.org/wiki/%E4%BA%8B%E5%8B%99%E9%9A%94%E9%9B%A2) 


* **MySQL如何实现隔离级别的（如可重复读的实现原理）（拼多多/字节跳动）** *`TODO`*
	* MySQL Inno DB 默认隔离级别 --> 可重复读
	* MVCC（多版本并发控制）（Inno DB引擎实现）
	* [InnoDB---可重复读隔离级别的底层实现原理](https://blog.csdn.net/huanghanqian/article/details/79517480)
	* [MySQL事务隔离级别的实现原理](https://www.cnblogs.com/cjsblog/p/8365921.html)
	* [轻松理解MYSQL MVCC 实现机制](https://blog.csdn.net/whoamiyang/article/details/51901888)


* **delete、 drop、truncate 的区别（PayPal）**
	* drop 直接删掉表（不再需要一张表的时候，用drop）
	* truncate 删除的是表中的数据，再插入数据时自增长的数据id又重新从1开始（保留表而删除所有数据的时候用truncate，实际是删除原来的表并重建一张新表）
	* delete 删除表中数据，可以在后面添加where字句（想删除部分数据行时候，用delete，并且带上where子句）
	* [SQL truncate 、delete与drop区别](https://www.cnblogs.com/8765h/archive/2011/11/25/2374167.html)

* **第一/第三/BC范式，以及我们实际建表时为什么要设计冗余字段，同时设计冗余字段会带来什么问题（阿里）**
	* 区分快照 & 冗余
	* [数据库设计冗余字段问题？](https://www.zhihu.com/question/50662784)
	* [如何解释关系数据库的第一第二第三范式？](https://www.zhihu.com/question/24696366) 

* **讲一下MySQL常见的数据库引擎（网易）**
  * [Mysql四种常见数据库引擎](https://yq.aliyun.com/articles/636314) 




### 索引

* **索引是什么，有哪些常见索引，以及为什么MySQL使用B+树做索引（字节跳动/腾讯/美团/星环/网易）**
	* 索引 --> 一种数据结构
	* B+ 树做索引的优势
		* 相较AVL, 红黑树等二叉树，这些查找过程中要进行许多次的磁盘读取操作，非常耗时（逻辑结构上相近的节点在物理结构上可能会差很远）
		* 较B树（字节跳动）
			* 相较于B树B+每个**非叶子**节点存储的关键字数更多，树的层级更少所以查询数据更快（层级更少）
			* B+所有关键字数据地址都存在**叶子**节点上，所以每次查找的次数都相同所以查询速度要比B树更稳定（更稳定）
			* B+树所有的**叶子**节点数据构成了一个有序链表，在查询大小区间（范围查询）的数据时候更方便，数据紧密性很高，缓存的命中率也会比B树高（天然具有排序）
			* B+树遍历整棵树只需要遍历所有的**叶子**节点即可，而不需要像B树一样需要对每一层进行遍历，这有利于数据库做全表扫描
	* [数据库索引到底是什么，是怎样工作的？](https://blog.csdn.net/weiliangliang111/article/details/51333169) 
	* [一步步分析为什么B+树适合作为索引的结构](https://blog.csdn.net/weixin_30531261/article/details/79312676)
	* [平衡二叉树、B树、B+树、B*树 理解其中一种你就都明白了](https://zhuanlan.zhihu.com/p/27700617)


* **聚集索引（Clustered Index）和非聚集索引的区别（拼多多/网易/字节跳动/Wish）**
	* 聚集索引 --> 指数据库表行中数据的物理顺序与键值的逻辑（索引）顺序相同
	* 每个表只能有一个聚集索引，因为目录只能按照一种方法进行排序
	* [聚集索引与非聚集索引的总结](https://www.imooc.com/article/22915) 
	* [聚合索引(clustered index) / 非聚合索引(nonclustered index)](https://blog.csdn.net/ak913/article/details/8026743)
	* [快速理解聚集索引和非聚集索引](https://blog.csdn.net/zc474235918/article/details/50580639)
	* [聚集索引 百度百科](https://baike.baidu.com/item/%E8%81%9A%E9%9B%86%E7%B4%A2%E5%BC%95) 


* **对于海量数据，如何提高查询效率（数据库优化策略）（野村证券）** *`TODO`* 
	* [优化1——数据库优化面试题](https://blog.csdn.net/u010796790/article/details/52194850) 
* **一个本来很快的SQL突然效率变慢，如何排查原因（阿里）**
* **MySQL索引不命中（索引失效）的可能原因及策略（美团/腾讯）**  *`TODO`* 
	* [MySQL索引无法命中的几种情况及索引验证方法](http://www.chinacion.cn/article/4907.html) 
* **MySQL联合索引命中情景分析（美团） **


* **InnoDB的索引结构（字节跳动）** 




### SQL语句相关

* **各种join操作的区别（left, right, inner join）** 
	* [mysql join操作](https://www.cnblogs.com/ggjucheng/archive/2012/11/06/2757972.html)
* **找出在表A中但不在表B中的记录（根据某一个共同的column）（PayPal）**
	* [查询A、B表中，A表中B表没有的数据](https://blog.csdn.net/long636/article/details/51733273)（三种方法）
* **having 和 where 用法上的区别（网易）**
  * [What is the difference between HAVING and WHERE in SQL?](https://stackoverflow.com/questions/287474/what-is-the-difference-between-having-and-where-in-sql) 


* **SQL优化策略**  *`TODO`* 
	
* [这大概是最全的sql优化方案了](https://zhuanlan.zhihu.com/p/48385127) 
	
* **慢查询的优化思路（字节跳动）** 

   

### MongoDB



## 计算机网络

* **描述三次握手四次挥手以及原因，每个包具体传递什么信息（阿里/腾讯/字节跳动）** 
	* 三次握手
		* 发送端 --> SYN
		* 接收端 --> [SYN/ACK]
		* 发送端 --> ACK
		* SYN（Synchronize Sequence Number） 是 TCP/IP 建立连接时使用的握手信号，置1表示有效
		* 需要三次握手原因：信息对等 && 防止超时（[《码出高效》](https://book.douban.com/subject/30333948/)  第一章）
		* 接收端回传SYN --> 告诉发送端我接收到的信息确实就是你所发送的信号
	* 四次挥手
		* 发送端 --> FIN (发送端进入 FIN-WAIT-1 （终止等待1）状态) 
		* 接收端 --> ACK (发送端收到接收端的确认请求后，进入 FIN-WAIT-2 （终止等待2）状态) 
		* 接收端 --> FIN（接收端进入半关闭状态 CLOST_WAIT）
		* 发送端 --> ACK（发送后，发送端进入 TIME-WAIT 状态）
	* [TCP的三次握手与四次挥手（详解+动图）](https://blog.csdn.net/qzcsu/article/details/72861891)
	* [“三次握手，四次挥手”你真的懂吗？](https://zhuanlan.zhihu.com/p/53374516) 


* **三次握手中SYN/ACK包的具体内容（腾讯）**
	* SYN --> 同步序列，用于建立连接过程
	* FIN --> Finish标志，用于释放连接，表示该报文段的发送方已经结束向对方发送数据
	* ACK --> 确认接收到的数据，确认序号标志
	* [TCP三次握手中SYN，ACK，Seq三者的关系](https://blog.csdn.net/u014507230/article/details/45310847)
	* [Understanding TCP Sequence and Acknowledgment Numbers](https://packetlife.net/blog/2010/jun/7/understanding-tcp-sequence-acknowledgment-numbers/)


* **用Socket描述TCP的三次握手（腾讯）** *`TODO`* 
	* [Socket过程详细解释（包括三次握手建立连接，四次握手断开连接）](https://blog.csdn.net/u013782203/article/details/51767763)（C++实现， *`TODO`* ）


* **网络间的进程如何表示（腾讯）** *`TODO`* 
	* [网络中进程之间如何通信](https://blog.csdn.net/bajiudongfeng/article/details/51568874) 

* **TCP和UDP的特点和区别（腾讯）**
	* TCP --> 面向连接 / UDP --> 无连接（发送数据前不需要建立连接）
	* TCP 提供可靠的服务（数据传输）/ UDP 无法保证
	* TCP --> 字节流 / UDP --> 数据报文段
	* [TCP和UDP的区别](https://zhuanlan.zhihu.com/p/24860273)
	* [常见面试题整理--计算机网络篇（每位开发者必备）](https://zhuanlan.zhihu.com/p/24001696)


* **TIME_WAIT状态产生（腾讯）** *`TODO`* 
	* [理解TIME_WAIT，彻底弄清解决TCP: time wait bucket table overflow](https://blog.51cto.com/benpaozhe/1767612)


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


* **DNS的过程（字节跳动）** 
* **HTTP 与 HTTPS 的区别（字节跳动）**  *`TODO`* 

  * HTTP协议以明文方式发送内容，不提供任何方式的数据加密
  * HTTPS其实就是建构在SSL（Secure Sockets Layer） / TLS之上的 HTTP协议
  * HTTPS密文传输 / HTTP 明文传输
  * HTTPS协议需要到CA申请证书
  * [详细解析 HTTP 与 HTTPS 的区别](https://juejin.im/entry/58d7635e5c497d0057fae036) 


* **描述HTTPS的加密过程（字节跳动）** 
* **对称加密&非对称加密在HTTPS加密过程中如何实践（字节跳动/阿里）** *`TODO`* 

  * [HTTPS加密过程和TLS证书验证](https://juejin.im/post/5a4f4884518825732b19a3ce)
  * [HTTPS中的TLS](https://github.com/Snailclimb/JavaGuide/blob/master/docs/network/HTTPS%E4%B8%AD%E7%9A%84TLS.md)（密码学角度）
  * [How does HTTPS work? What's a CA? What's a self-signed Certificate?](https://www.youtube.com/watch?v=T4Df5_cojAs) （HTTPS工作流程举例，需要时再看 *`TODO`* ）


* **HTTP代理如何实现（阿里）** *`TODO`* 
	* [如何实现一个HTTP/HTTPS代理客户端 ](https://github.com/fwon/blog/issues/38)


* **描述SSO的原理（拼多多）** *`TODO`*
	* [CAS实现单点登录SSO执行原理探究(终于明白了)](https://blog.csdn.net/javaloveiphone/article/details/52439613)
	* [How does single sign-on work?](https://www.onelogin.com/learn/how-single-sign-on-works) *`TODO`*
* **网络拥塞的解决方案（字节跳动）** 

  * [网络拥塞成因与处理](https://blog.csdn.net/oZhuZhiYuan/article/details/52167246) 
* **介绍 OSI 七层模型**
  * 应用层（应用层 --> 表示层 --> 会话层） --> 传输层 --> 网络层 --> 数据链路层 --> 物理层 (7层)
  * 应用层 --> 传输层 --> 网络层 --> 数据链路层 --> 物理层 （5层）
  * 并非标准，一个概念性框架
  * [OSI七层模型详解](https://blog.csdn.net/yaopeng_2005/article/details/7064869)
  * [干货：计算机网络知识总结.md](https://github.com/Snailclimb/JavaGuide/blob/master/docs/network/%E5%B9%B2%E8%B4%A7%EF%BC%9A%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%9F%A5%E8%AF%86%E6%80%BB%E7%BB%93.md#%E4%B8%80%E8%AE%A1%E7%AE%97%E6%9C%BA%E6%A6%82%E8%BF%B0)（逐层术语解释）


* **描述Session的实现原理（或者如何设计一个Session）（拼多多）** *`TODO`*

* **如何保证token不被劫持和篡改（大概意思，项目相关）（微软）**   `TODO`


    * Challenge Value，加盐值（防止彩虹表攻击）
    * 采用HTTPS
* **业界有哪些网络认证的方法（基于设备认证项目提问）（阿里）** 



## Linux相关

* cpu load 和 cpu utilization的区别（阿里）

* top，load 指令，free 中 cached和buffers的区别（阿里）
* 找出某目录下文件中带电子邮箱的文件（爱奇艺）
* 杀死所有Java进程
	* `ps -ef | grep java | grep -v grep | awk '{print $2}' | xargs kill -9`
	* [Linux 杀掉所有Java进程](https://blog.csdn.net/u011517841/article/details/79781830) 
* 干掉占用某端口的服务（网易）
  * [linux杀死占用某端口的所有进程](https://blog.csdn.net/lissdy/article/details/70256032)
* 打印一个文本中出现次数前十的数据（腾讯）




## 框架&工具篇

### Spring

* **描述Spring的IoC**
  * IoC是一种思想，并非一个具体技术
    * 基于 **依赖倒置原则（Dependency Inversion Principle）**
      * 把原本的高层建筑依赖底层建筑“倒置”过来，变成底层建筑依赖高层建筑。高层建筑决定需要什么，底层去实现这样的需求，但是高层并不用管底层是怎么实现的。这样就不会出现前面的“牵一发动全身”的情况
    * 将原本在程序中手动创建对象的控制权，交由Spring框架来管理
    * 反转 --> 由 **IoC容器** 来帮忙创建及注入依赖对象（Spring 提供 BeanFactory 和 ApplicationContext 两种容器）
      * BeanFactory 和 ApplicationContext 的区别（依图）
        * BeanFactory 为含有 bean 集合的工厂类
        * ApplicationContext 接口是由 BeanFactory 接口派生出来的，所以提供了 BeanFactory 的所有功能
    * 实现 --> 依赖注入（相对 IoC 而言，“依赖注入” 明确描述了 “被注入对象依赖IoC容器配置依赖对象”）
  * 依赖注入，就是 **把底层类作为参数传入上层类，实现上层类对下层类的“控制”**
    * 谁依赖于谁：当然是应用程序依赖于IoC容器
    * 为什么需要依赖：应用程序需要IoC容器来提供对象需要的外部资源
    * 谁注入谁：很明显是IoC容器注入应用程序某个对象，应用程序依赖的对象
    * 注入了什么：就是注入某个对象所需要的外部资源（包括对象、资源、常量数据）
  * 好处
    * 让你脱离对依赖对象的维护，只需要随用随取，不需要关心依赖对象的任何过程
    * 可以有效地改善模块之间的紧耦合问题
  * 源码阅读问题（星环）*`TODO`* 
  * [IoC-spring 的灵魂(带你轻松理解IOC思想及bean对象的生成过程)](https://juejin.im/post/593386ca2f301e00584f8036)（基本概念）
  * [【第二章】 IoC 之 2.1 IoC基础 ——跟我学Spring3](https://jinnianshilongnian.iteye.com/blog/1413846)（IoC思想详解）
  * [Spring IoC有什么好处呢？](https://www.zhihu.com/question/23277575/answer/169698662)（汽车的例子有助于理解IoC）
  * [Inversion of Control Containers and the Dependency Injection pattern](https://martinfowler.com/articles/injection.html)（Martin文章 *`TODO`*）
  * [Spring IOC 容器源码分析](https://javadoop.com/post/spring-ioc)（源码阅读 *`TODO`*）
  * [What is difference between BeanFactory and ApplicationContext in Spring framework](https://javarevisited.blogspot.com/2012/11/difference-between-beanfactory-vs-applicationcontext-spring-framework.html) *`TODO`*


* **什么是Bean以及描述Bean的生命周期（美团/网易）**
  * 在 Spring 中，构成应用程序主干并由Spring IoC容器管理的对象称为Bean。一个Bean是一个由Spring IoC容器实例化、组装和管理的对象
  * 生命周期
    * 创建Bean
      * 实例化 Bean 对象
      * 设置属性
      * 检查 Aware 相关接口并注入依赖（具体包括 BeanNameAware、BeanFactoryAware 和 ApplicationContextAware，分别注入Bean ID， Bean Factory 或 ApplicationContext）
      * 调用 BeanPostProcessor 的前置初始化方法 postProcessBeforeInitialization
      * 如果实现了 InitializingBean 接口，则会调用 afterPropertiesSet 方法
      * 调用 Bean 自身定义的 init 方法
      * 调用 BeanPostProcessor 的后置初始化方法 postProcessAfterInitialization
      * 创建过程完毕
    * 销毁
      * Spring Bean 的销毁过程会依次调用 DisposableBean 的 destroy 方法和 Bean 自身定制的 destroy 方法
  * [Spring Bean是什么？](https://www.awaimai.com/2596.html)
  * [第37讲 | 谈谈Spring Bean的生命周期和作用域？](https://time.geekbang.org/column/article/12472)

* **描述Spring的AOP（小红书）** 
  * AOP的理念
    * 将分散在各个业务逻辑代码中 相同的代码 通过 **横向切割** 的方式抽取到一个独立的模块中（模块化）
    * 将相同逻辑的重复代码横向抽取出来，使用动态代理技术将这些重复代码**织入**到目标对象方法中，实现和原来一样的功能
  * 基本概念
    * 通知（advice） --> 切面的工作被称为通知，定义了切面是什么以及何时被使用
    * 连接点（join point） --> 应用执行过程中能够插入切面的一个点，可以是方法调用时，抛出异常时等等
    * 切点（pointcut） --> 需要应用切面的方法（具体定位的连接点）
    * 切面（aspect） --> 切面是 通知 和 切点 的结合，共同定义：是什么，在何时和何处完成其功能
    * 织入(weaving) --> 把切面应用到目标函数的过程
  * 好处
    * 显示地声明在何处如何应用该行为，有效减少代码冗余，让类更加关注自身主要功能
  * Spring AOP 具体实现（源码级别）*`TODO`*
    * Java JDK 动态代理 （默认）
    * CGLIB 动态代理
  * 爱奇艺项目中AOP的实现（切面设计）（eBay）
    * @Before，判断模板有效性等
  * [关于 Spring AOP (AspectJ) 你该知晓的一切](https://blog.csdn.net/javazejian/article/details/56267036)（AOP入门 + 应用场景 + Spring中的基本实现）
  * [《Spring设计思想》AOP设计基本原理](https://blog.csdn.net/luanlouis/article/details/51095702)（从程序运行角度解释AOP的工作原理）
  * 《Spring实战（第四版）》第四章
  * [Spring AOP就是这么简单啦](https://juejin.im/post/5b06bf2df265da0de2574ee1)（可在面试前看的纯干货）
  * [《Spring设计思想》AOP实现原理（基于JDK和基于CGLIB）](https://blog.csdn.net/luanlouis/article/details/51155821) （Spring AOP的完整实现过程 *`TODO`*）


* **简述Spring Boot框架**
  * 核心
    * 自动配置
    * 起步依赖
  * 从本质上来说，Spring Boot就是Spring，它做了那些没有它你自己也会去做的Spring Bean配置
  * 《Spring Boot实战》前三章


* **描述一个Spring Boot项目的启动过程（阿里）**
  * @SpringBootApplication --> 复合注解（@SpringBootConfiguration / @EnableAutoConfiguration / @ComponentScan）
  * [SpringBoot 应用程序启动过程探秘](https://juejin.im/post/5b8f05a5f265da43296c6102)


* **什么是JPA**
  * [Java持久化API Wiki](https://zh.wikipedia.org/wiki/Java%E6%8C%81%E4%B9%85%E5%8C%96API)


* **什么是Spring注解，Spring中有哪些常用的注解，以及注解自身是如何实现的（阿里/字节跳动）** *`TODO`*
  * 注解 --> 减少配置文件内容
  * [Java annotation Wiki](https://en.wikipedia.org/wiki/Java_annotation)
  * [秒懂，Java 注解 （Annotation）你可以这样学](https://blog.csdn.net/briblue/article/details/73824058)（简单理解： 注解 --> 标签）
  * [精进Spring—Spring常用注解](https://blog.csdn.net/u010648555/article/details/76299467)（常见注解）



### Vue.js



### kafka *`TODO`*

* 基于发布-订阅模式(publish-subscribe)
* 术语
	* topic
		* A topic is a category or feed name to which records are published
	* partition
		* Each partition is an ordered, immutable sequence of records that is continually appended to a structured commit log
		* offset
* 特征
	* stronger ordering guarantees ("exclusive consumer")
* kafka Stream
	* QuickStart
		* ZooKeeper server
		* Kafka server
		* Start Application (eg: WordCount)
		* Producer & Consumer
	* [Kafka Streams](https://kafka.apache.org/23/documentation/streams/)
	* [Introduction](http://kafka.apache.org/intro)
	* [kafka解决了什么问题?](https://www.zhihu.com/question/53331259)
	* [《Apache Kafka实战》](https://book.douban.com/subject/30221096/)
	* [消息队列其实很简单](https://github.com/Snailclimb/JavaGuide/blob/master/docs/system-design/data-communication/message-queue.md)（扫盲篇）



### Elasticsearch *`TODO`*

* ES的索引是怎么实现的（爱奇艺）



### redis *`TODO`*



### swagger *`TODO`*



### Netty *`TODO`*



## Android

### 关键类

### App生命周期

### 主要组件

### AIDL通讯

### 回调




## 其他

* **浅拷贝 & 深拷贝（字节跳动）**
	* 浅拷贝 --> 对基本数据类型进行值传递，对引用数据类型进行引用传递般的拷贝，**没有真实的创建一个新的对象**
	* 深拷贝 --> 对基本数据类型进行值传递，对引用数据类型，**创建一个新的对象**，并复制其内容
	* [细说 Java 的深拷贝和浅拷贝](https://segmentfault.com/a/1190000010648514) 
	* [8.6: Pass by Value vs. Pass by Reference - Processing Tutorial](https://www.youtube.com/watch?v=hNR6fsksEu8)
* **值传递 & 引用传递**
  * Java中方法参数传递方式是按**值传递**
  * 如果参数是基本类型，传递的是基本类型的字面量值的拷贝
  * 如果参数是引用类型，传递的是该参量所引用的对象在堆中地址值的拷贝
  * [什么是值传递和引用传递？](https://www.zhihu.com/question/31203609/answer/50992895) 
* **git rebase 和 git merge 有什么区别（小红书/野村证券/PayPal）**
	* 同：都是用于从一个分支获取并且合并到当前分支
	* 异：rebase --> 会合并之前的commit历史（带有破坏性的修改 commit 历史的命令）
	* 一个干净的，没有merge commit的线性历史树 --> git rebase
	* 保留完整的历史记录，并且想要避免重写commit history的风险 --> git merge
	* [git rebase 和 git merge 的区别](https://www.jianshu.com/p/f23f72251abc) 


* **git fetch 和 git pull 有什么区别（PayPal）**
	* pull = fetch + merge
	* [详解git fetch与git pull的区别](https://blog.csdn.net/riddle1981/article/details/74938111)


* **描述 git 中的 cherry-pick 指令（小红书）**  *`TODO`* 


* **描述微服务架构（携程）**  *`TODO`*

