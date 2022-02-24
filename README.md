# 500-interview-question-for-programmers

## 概述

对我而言，这是个人整理平时工作和面试中碰到的一些实际问题的一份手册（持续维护）；对你而言，这可以作为一份可参考的面试手册。

优势是这里罗列的基本都是大公司的实际面试题或者个人工作中的总结输出，且由于面试公司较多，比较全面，对准备面试有一定参考价值；

劣势是当前阶段还不够深入，很多问题你可能需要再看原始的文档或者源码才能获得更深的理解（当然我也会尽量整理一些链接附上），**你不太可能仅仅通过本页面就获得非常有见地的观点**。

模块间排序一般无特定意义（每个模块开头一般会写一句话小结），模块内主要按面试频次排序。

如果觉得有帮助，请 `Star` ，善用 `Ctrl` + `F` :)

**TAGS** 

*`HARD`* --> 一般需要有实操经验才能答得比较好

*`TODO`* --> 内容待进一步优化

## 算法和设计


* 详见 [科学刷题指北](科学刷题指北.md)



## Java

### 基础问题

（一些Java的基础问题，面试一般由可由这些点切入，由浅入深。）


* **序列化（Serialization）和反序列化（小红书）**

  * [Java 序列化](https://www.runoob.com/java/java-serialization.html)（基本介绍）
  * [二叉树的序列化与反序列化](https://leetcode-cn.com/problems/serialize-and-deserialize-binary-tree/) （经典coding题）
* **Java中父类和子类初始化顺序（小红书）**
  * [java中父类和子类初始化顺序](https://blog.csdn.net/yuxin6866/article/details/53107578) 


* **描述 Java8及之后的新特性（星环） / Java 17有什么新特性（小红书）**
  * 开放题，如 lambda 表达式，Stream 编程 等
  * [What's New in JDK 8](https://www.oracle.com/java/technologies/javase/8-whats-new.html)
  * [Stream (Java Platform SE 8 ) - Oracle Help Center](https://docs.oracle.com/javase/8/docs/api/java/util/stream/Stream.html) 


* **关键字** 
  * ***finally***
    * try-catch-finally 中包含 return 的情况分析（字节跳动）
      * [Multiple returns: Which one sets the final return value?](https://stackoverflow.com/questions/2309964/multiple-returns-which-one-sets-the-final-return-value)
      * “不要在 finally 代码块中使用 return 语句”（ [《码出高效》](https://book.douban.com/subject/30333948/)  5.2）
  * ***static***
    * the keyword static indicates that the particular member belongs to a type itself, rather than to an instance of that type
    * [A Guide to the Static Keyword in Java](https://www.baeldung.com/java-static)
* **字符串相关类**
  * 常见问题如 StringBuffer，StringBuilder 差别，进而扩展到如线程安全等相关问题
  * [第5讲 | String、StringBuffer、StringBuilder有什么区别？](https://time.geekbang.org/column/article/7349)
* **什么是反射 && 反射的具体应用**
  * 可从概念，使用，应用场景等几个方面考察，由浅入深
  * [详解面试中常考的 Java 反射机制](https://zhuanlan.zhihu.com/p/86293659) （参考1）
  * [Guide to Java Reflection](https://www.baeldung.com/java-reflection) （参考2）



### IO相关

（这部分深挖可以问得很难，一般可从常见IO模型，适用场景开始，到Java中的IO模型实现，深入到框架的实现。）*`TODO`* *`HARD`*

* **描述BIO / NIO（网易）/ 描述常见的IO模型（小红书）** 
  * [The difference between BIO and NIO, AIO](https://www.programmersought.com/article/10551850908/) （一些基本的概念解释）
  * [怎样理解阻塞非阻塞与同步异步的区别？](https://www.zhihu.com/question/19732473/answer/241673170) （评价很高的答案，从操作系统本身进行解释）
* **Java提供了哪些IO方式（拼多多/字节跳动）** 
  * BIO / NIO / AIO
  * [Java NIO浅析](https://tech.meituan.com/2016/11/04/nio.html)
  * [第11讲 | Java提供了哪些IO方式？ NIO如何实现多路复用？](https://time.geekbang.org/column/article/8369)
  * [Java NIO Tutorial](http://tutorials.jenkov.com/java-nio/index.html) （一份实操教程）
  * [Lesson: Basic I/O](https://docs.oracle.com/javase/tutorial/essential/io/index.html)（官方 Docs）

* **描述Spring中的IO方式（字节跳动）**
* **select 和 epoll 的区别（字节跳动）**  
  * [select和epoll区别](https://www.jianshu.com/p/430141f95ddb) 



### 集合框架

（Java常见八股，可以作为你是否有过一些源码阅读的基础，也可能会和线程安全等内容结合来问。）

* **描述 HashMap 的底层实现（远景智能/字节跳动/百度/喜马拉雅）**
  * 一般可以从基本方法，capacity / load factor 作用及配置，如何解决哈希冲突，为什么HashMap不是线程安全的等方面展开
  * [Java HashMap工作原理及实现](https://yikun.github.io/2015/04/01/Java-HashMap%E5%B7%A5%E4%BD%9C%E5%8E%9F%E7%90%86%E5%8F%8A%E5%AE%9E%E7%8E%B0/) （基本参考）
  * [Java 8系列之重新认识HashMap](https://tech.meituan.com/2016/06/24/java-hashmap.html) （主要参考）
  * [Class HashMap<K,V>](https://docs.oracle.com/javase/8/docs/api/java/util/HashMap.html) （Java 8 Docs）
  * [Java源码分析：关于 HashMap 1.8 的重大更新](https://blog.csdn.net/carson_ho/article/details/79373134)（1.7 vs 1.8 详细比较）


* **ConcurrentHashMap 实现原理，或者说它是怎么保证线程安全的（星环/字节跳动/阿里）**
	
	* 一般是上一个提问的进阶提问
	* [HashMap? ConcurrentHashMap? 相信看完这篇没人能难住你！](https://crossoverjie.top/2018/07/23/java-senior/ConcurrentHashMap/)
	* [深入浅出ConcurrentHashMap1.8](https://www.jianshu.com/p/c0642afe03e0)（1.8版本的详细解释）
	* [老生常谈，HashMap的死循环](https://juejin.im/post/5a66a08d5188253dc3321da0)（具体分析 非线程安全带来的无限循环占用 CPU100% 问题）
	* [ConcurrentHashMap in Java](https://www.geeksforgeeks.org/concurrenthashmap-in-java/)
	* [A Guide to ConcurrentMap](https://www.baeldung.com/java-concurrent-map)
	


* **HashMap 和 TreeMap 的区别和应用场景（PayPal/依图）**
  * [HashMap和TreeMap区别详解以及底层实现](https://blog.csdn.net/xlgen157387/article/details/47907721)（概念+比较）
  * [第9讲 | 对比Hashtable、HashMap、TreeMap有什么不同？ ](https://time.geekbang.org/column/article/8053) （概念+源码分析） 
* **HashSet 如何判断重复元素（小红书/喜马拉雅）**
  * [HashSet重复元素判断](https://itfafa.iteye.com/blog/1698690) 
  * [Java提高篇——equals()与hashCode()方法详解](https://www.cnblogs.com/Qian123/p/5703507.html) 
* **ArrayList和LinkedList的区别（源码级别）（字节跳动）** 



### JVM相关

（Java常见八股，深入可以涉及到JVM调优，OOM等相关内容。）

* **描述Java的内存模型（阿里/美团/网易）** 

  * 可回答JVM对内存区域的划分，由于JVM支持多线程同时执行，我一般从线程私有和线程共享两个方面回答，水平一般（自己也没什么经验）的面试官听完一般也就结束了。

    - 程序计数器（Program Counter Register） --> 可以看做是当前线程所执行的字节码的行号指示器（字节码解释器工作时通过改变这个计数器的值来选取下一条需要执行的字节码指令）

    - 虚拟机栈（Virtual Machine Stack） --> 方法执行时创建**栈帧（Stack Frame）**，对应着一次次的 Java **方法调用**

    - 本地方法栈（Native Method Stack） --> 和虚拟机栈类似，区别为虚拟机栈为虚拟机执行Java方法（也就是字节码）服务，而本地方法栈为虚拟机使用到的Native方法服务（甚至有的Java虚拟机（譬如Hot-Spot虚拟机）直接把 本地方法栈 和 虚拟机栈 合二为一）

       ( ↑（线程私有）--- （线程共享） ↓ )

    - 堆（Heap） --> 虚拟机管理的内存中最大的一块，所有线程共享的内存区域，“几乎”所有的 **对象实例** 都在这里分配内存

    - 方法区（Method Area） --> 所有线程共享的一块内存区域，用于存储所谓的元（Meta）数据，如类结构信息，以及对应的运行时常量池、字段、方法代码等 
    - 运行时常量池（Run-Time Constant Pool） --> 属于方法区的一部分，存放各种常量信息

  * [The Structure of the Java Virtual Machine](https://docs.oracle.com/javase/specs/jvms/se9/html/jvms-2.html)（官方 Docs）

  * 《深入理解Java虚拟机》 第三版 2.2

  * [Java内存模型（JMM）总结](https://zhuanlan.zhihu.com/p/29881777)

* **描述GC（百度/美团/Soul）**

  * 一般八股回答即可，如果没有指定问题，我一般从GC这件事情本身开始谈（抛开语言），真正有实战的面试官可能会继续追问调优策略和指令区别。
  * 对象存活判断
    * 引用计数算法，无法解决对象相互循环引用的问题，Java中没有使用（在 Python GC等场景有应用）
    * 可达性分析算法（如果某个对象到GC Roots间没有任何引用链相连， 则证明此对象是不可能再被使用的。GC Roots --> 虚拟机栈和本地方法栈中正在引用的对象、静态属性引用的对象和常量）
  * 垃圾收集算法
    * 标记-清除算法（Mark-Sweep） -->首先标记出所有需要回收的对象，在标记完成后，统一回收掉所有被标记的对象。执行效率不稳定 && 内存碎片化问题
    * 标记-复制算法（Copying） --> 将内存分为大小相同的两块（“半区复制”），每次使用其中的一块。每次将活着的对象复制到 另一块区域，拷贝过程中将对象顺序放置，避免内存碎片化，代价是将可用内存缩小为了原来的一半
    * 标记-整理算法（Mark-Compact） --> 类似于标记-清除，但为了避免内存碎片化，”移动式”的。清理过程中移动对象，以确保移动后的对象占用连续的内存空间
    * 分代收集算法 --> 根据对象存活周期的不同将内存分为几块 （eg: 新生代/老生代）
  * 频繁的 Full GC 怎么排查（阿里）
  * Full GC 和 Minor GC 的区别（阿里）
  * 《深入理解Java虚拟机》第三版 第3章
  * [Java Garbage Collection Basics](https://www.oracle.com/webfolder/technetwork/tutorials/obe/java/gc01/index.html) (Oracle Guides)
  * [Garbage Collection in Java – What is GC and How it Works in the JVM](https://www.freecodecamp.org/news/garbage-collection-in-java-what-is-gc-and-how-it-works-in-the-jvm/)
  * [jvm系列(三):GC算法 垃圾收集器](https://mp.weixin.qq.com/s?__biz=MzI4NDY5Mjc1Mg==&mid=2247483952&idx=1&sn=ea12792a9b7c67baddfaf425d8272d33&chksm=ebf6da4fdc815359869107a4acd15538b3596ba006b4005b216688b69372650dbd18c0184643&scene=21#wechat_redirect)
  * [咱们从头到尾说一次 Java 垃圾回收](https://mp.weixin.qq.com/s/aA1eDYIUHuIfigTw2ffouw)

* **工作中JVM内存调优的经验和工具**


    * App内存基线调优（数据类型转换 / 静态资源压缩 / 池化资源及时释放等）


    * 知道一些常见的JVM调优指令，但没有实际使用案例（jmap / jstack 等）*`TODO`*



* **描述 Java 中的类加载过程（阿里/星环）**

  * 这部分可以答类加载的步骤，以及每个步骤的具体行为，记忆即可。简单总结：
    * 加载（Loading） --> 链接（Linking） --> 初始化（Initializing）
    * 加载（Loading）
      * 将字节码数据从不同的数据源读取到 JVM 中，并映射为 JVM 认可的数据结构（Class对象），用户可以自定义类加载器（用户参与），实现类加载过程
    * 链接（Linking） --> 把原始的类定义信息平滑地转化到JVM运行的过程中，细分为：
      * 验证（Verification） --> 确保Class文件的字节流中包含的信息符合JVM的全部约束要求，保证这些信息被当做代码后不会危害虚拟机自身的安全
      * 准备（Preparation） --> 正式为类变量分配内存并设置类变量初始值的阶段
      * 解析（Resolution） --> 虚拟机将常量池内的符号引用替换为直接引用的过程（直接引用是可以直接指向目标的指针、相对偏移量或者是一个能间接定位到目标的句柄）
    * 初始化（Initializing）
      * 真正执行类中定义的 Java 程序代码(字节码)，初始化阶段就是执行类构造器 <clinit>() 方法（Javac编译器的自动生成物）的过程。 （《深入理解Java虚拟机》第三版 P277）
    
  * 一般会继续追问到 Parents Delegation Model（宜译作“溯源委派加载模型”（[《码出高效》](https://book.douban.com/subject/30333948/) P119）
    * 概念，好处，实现等
    
    * 如果一个类加载器收到了类加载的请求，它首先不会自己去尝试加载这个类，而是把这个请求委派给父类加载器去完成，每一个层次的类加载都是如此，因此所有的加载请求最终都应该传送到最顶层的启动类加载器中，只有当父加载器反馈自己无法完成这个加载请求时，子加载器才会尝试自己去完成加载
    
    * 好处 --> Java中的类随着它的加载器一起具备了一种带有优先级的层次关系，避免类的重复加载
    
    * 实现
    
      1. 检查请求加载的类型是否已经被加载过，没有则调用父加载器的 loadClass() 方法
    
      2. 若父加载器为空则默认使用启动类加载器作为父加载器
    
      3. 加入父类加载器加载失败，抛出ClassNotFoundException，才调用自己的 findClass() 方法尝试进行加载
    
    * 为什么要用双亲委派模型，有没有别的实现，或者说Java为什么要这么设计（阿里）*`TODO`*
    
  * [第23讲 | 请介绍类加载过程，什么是双亲委派模型？](https://time.geekbang.org/column/article/9946)（简介 + 各步骤实例）

  * [Java Virtual Machine Specification Chapter 5. Loading, Linking, and Initializing](https://docs.oracle.com/javase/specs/jvms/se8/html/jvms-5.html)（官方JVM虚拟机规范 Docs）

  * 《深入理解Java虚拟机：JVM高级特性与最佳实践》第7章 -- 虚拟机类加载机制

* **描述 Java 中的类加载机制（星环）**
  * Java虚拟机把描述类的数据从Class文件加载到内存，并对数据进行校验、转换解析和初始化，最终形成可以被虚拟机直接使用的Java类型，这个过程被称作虚拟机的类加载机制（《深入理解Java虚拟机》第三版 P262）


* **描述JVM中常见的垃圾回收器，如CMS，以及JVM调优思路（美团）** 
	* [一文了解JVM全部垃圾回收器，从Serial到ZGC](https://juejin.im/post/5bade237e51d450ea401fd71)
	* [第27讲 | Java常见的垃圾收集器有哪些？](https://time.geekbang.org/column/article/10513)
	* [《码出高效》](https://book.douban.com/subject/30333948/)  P134~P138


* **Java中什么时候会发生OOM（华为）** 
  * 除了程序计数器，虚拟机内存的其他几个运行时区域都有可能发生OOM异常的可能
  * 《深入理解Java虚拟机》第三版 2.4
  * [Java内存溢出(OOM)异常完全指南](https://www.jianshu.com/p/2fdee831ed03) 
* **NoClassDefFoundError和ClassNotFoundException的场景和解决办法（星环）**
* **如何判断内存泄漏（腾讯）**
  * 因为长生命周期持有它的引用而导致不能被回收，这就是Java中内存泄漏的发生场景
  * [Java内存泄漏分析和解决](https://www.jianshu.com/p/54b5da7c6816)
* **CPU使用率突然升高如何排查（Soul）** 
  * 其实是想问JVM相关的内容
* **已知某个类的路径，如何在代码中实例化这个类（星环）** 
  * 获取 Class对象 + newInstance() 实例化
  * [根据指定类名创建实例（Java的反射机制）](https://blog.csdn.net/u010729348/article/details/16819693) 
* **如何自定义类加载器** 
  * [JVM——自定义类加载器](https://blog.csdn.net/SEU_Calvin/article/details/52315125) 



### Java并发编程

（常见八股，如果没有海量并发经验的话（像我Orz），一般会从概念到源码，问到答不上为止。）

* **描述Java下的并发编程（阿里）**
	* Java中实现并发编程的手段 --> 多线程
	* 线程的生命周期（新建 / 就绪 / 运行 / 阻塞 / 死亡）（网易）
	  * 线程阻塞和等待的区别（网易）
	  * [Java线程的生命周期](https://juejin.cn/post/6844903558433734669) 
	  * [Difference between WAIT and BLOCKED thread states](https://stackoverflow.com/questions/15680422/difference-between-wait-and-blocked-thread-states) 
	* 创建线程的方法（阿里）
		* Runnable 接口
		* 继承 Thread
		* 通过 Callable 和 Future 创建线程
	* [Java 多线程编程](https://www.runoob.com/java/java-multithreading.html) （生命周期）


* **synchronized 和 volatile（字节跳动/阿里/网易/爱奇艺）**
  * synchronized 一般会问如何使用，底层实现等
  * volatile 一般会问实现，可见性，指令重排等
    * 只能用于变量（is used to mark a Java variable as "being stored in main memory"）
    * 保证变量的可见性（指示 JVM，这个变量是不稳定的，每次使用它都到主存中进行读取） && 防止指令重排序
    * 对一个 volatile 变量的写操作， Happens-Before 后续对这个 volatile 变量的读操作
  * [Difference Between Atomic, Volatile and Synchronized in Java](https://www.geeksforgeeks.org/difference-between-atomic-volatile-and-synchronized-in-java/)（概述）
  * [Java Volatile Keyword](http://tutorials.jenkov.com/java-concurrency/volatile.html) （volatile tutorial）
  * [synchronized 实现原理](https://xiaomi-info.github.io/2020/03/24/synchronized/)
* **描述 synchronized 和 wait() 搭配使用的场景（星环）** 
  * 为什么 synchronized 要搭配 wait() 使用，见 [Java: Why wait must be called in a synchronized block](https://programming.guide/java/why-wait-must-be-in-synchronized.html)


* **ReentrantLock 源码阅读（网易/小红书/星环）**
  * 可重入 --> 当一个线程试图获取一个它已经获取的锁时，这个获取动作就自动成功（自己可以再次获取自己的内部锁）
  * 描述 AQS（AbstractQueuedSynchronizer）的作用（另一种问法为 “ReentrantLock里提供了一个很好的工具，你知道这个工具是什么吗？”）
  * 可从基本思想，主要方法，实现细节等 narrow down
  * [从ReentrantLock的实现看AQS的原理及应用](https://tech.meituan.com/2019/12/05/aqs-theory-and-apply.html)
  * [Class AbstractQueuedSynchronizer](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/locks/AbstractQueuedSynchronizer.html)
* **synchronized和Lock的比较（使用/性能/效率），以及为什么会有这种差别（字节跳动）** *`TODO`*
* 这个问题等于上述两个一起问了，可分别解答
* **Java中如何使用线程池，线程池有哪些参数（阿里/字节跳动/喜马拉雅） ， 线程池有哪些类型（百度）**
  * 线程池的好处（另一种问法是 “我每次创建线程就可以了，为什么要用线程池？”）
    * 降低资源消耗 / 提高响应速度 / 提高线程的可管理性 / 提供可扩展功能 等
  * ThreadPoolExecutor类
    * 线程池中的每一个线程被封装成一个 Worker 对象，ThreadPool 维护的其实就是一组 Worker 对象
    * 一些主要参数（线程分配 && 任务分配）
      * corePoolSize --> 核心线程数
      * maximumPoolSize --> 最大能创建的线程数（可以理解为当任务量突然过大时的一种补救措施）
      * workQueue --> 工作队列，为 BlockingQueue，用于存储等待执行的任务
      * keepAliveTime
      * threadFactory --> 如何定义创建线程，如命名等
      * handler --> 拒绝策略
    * 参数配置
      * IO密集型 和 计算密集型 任务如何配置线程池参数（字节跳动）/ 线程池参数配置策略及原因（喜马拉雅/拼多多/阿里）
        * 实际业务需求预估
        * IO密集型 和 计算密集型 的经验值配置 (如 《Java并发编程》，经验值)
        * 运行时动态化配置（[Java线程池实现原理及其在美团业务中的实践](https://tech.meituan.com/2020/04/02/java-pooling-pratice-in-meituan.html) ）
  * [Java线程池实现原理及其在美团业务中的实践](https://tech.meituan.com/2020/04/02/java-pooling-pratice-in-meituan.html) 
  * [22 | Executor与线程池：如何创建正确的线程池？](https://time.geekbang.org/column/article/90771)（基本介绍和主要参数）
  * [深入理解 Java 线程池：ThreadPoolExecutor](https://juejin.im/entry/58fada5d570c350058d3aaad)（ThreadPoolExecutor 源码和关键类分析）
  * [第21讲 | Java并发类库提供的线程池有哪几种？ 分别有什么特点？](https://time.geekbang.org/column/article/9712)（介绍 Executor 框架和从设计角度介绍ThreadPoolExecutor类）
  * [《码出高效》](https://book.douban.com/subject/30333948/)  7.4.2（线程池源码详解，关键方法逐行解释）


* **乐观锁与悲观锁的概念，常见实现（阿里）**
	* 乐观锁适用于**多读**的应用类型，这样可以提高吞吐量 / 悲观锁适合于**多写**
	* 乐观锁常见实现 --> 版本号机制 / CAS 算法
		* CAS 算法概念 / 缺点
			* 自旋 --> 循环尝试
			* ABA 问题
	* [何谓悲观锁与乐观锁](https://github.com/Snailclimb/JavaGuide/blob/master/docs/essential-content-for-interview/%E9%9D%A2%E8%AF%95%E5%BF%85%E5%A4%87%E4%B9%8B%E4%B9%90%E8%A7%82%E9%94%81%E4%B8%8E%E6%82%B2%E8%A7%82%E9%94%81.md) （基本介绍）
	* [Optimistic vs. Pessimistic locking](https://stackoverflow.com/questions/129329/optimistic-vs-pessimistic-locking)


* **描述ThreadLocal 的实现（美团），什么情况ThreadLocal会发生OOM（星环）**
  * "它通常用于同一个线程内，跨类、跨方法传递数据"
  * [Java ThreadLocal](http://tutorials.jenkov.com/java-concurrency/threadlocal.html) 
  * [《码出高效》](https://book.douban.com/subject/30333948/)  7.5
* **描述 Atomic 类的底层实现（美团）** 
* **sleep()和wait()的区别，应用场景（字节跳动）** 
  * [Difference between Wait and Sleep, Yield in Java](https://javarevisited.blogspot.com/2011/12/difference-between-wait-sleep-yield.html#axzz6jzKp3QZM) 


* **什么是线程安全**
  * a class is thread safe when it continues to behave correctly when accessed from multiple threads
  * 指某个函数、函数库在多线程环境中被调用时，能够正确地处理多个线程之间的共享变量，使程序功能正确完成
  * [线程安全 Wiki](https://zh.wikipedia.org/wiki/%E7%BA%BF%E7%A8%8B%E5%AE%89%E5%85%A8) 
* **join() 方法的作用**
  * Thread.join() 把指定的线程加入到当前线程，可以将两个交替执行的线程合并为顺序执行的线程。比如在线程B中调用了线程A的join()方法，直到线程A执行完毕后，才会继续执行线程B
  * [Java多线程中join方法的理解](https://uule.iteye.com/blog/1101994)
  * [简谈Java的join()方法](https://www.cnblogs.com/techyc/p/3286678.html)  



## Python

（由于国内Python Web开发岗位较少，所以碰到的Python的实际面试问题不多，这里只罗列基本的面试问题。由于我有些Python Web开发经验，其实Python也有很多能问的东西）。


* **Python里如何实现真正的多线程（阿里/腾讯）**  
* **给一段Python代码，有哪些优化思路和策略（阿里）**   


* **Python爬虫中存在环引用该如何处理（阿里）** 
* **如何写一个程序计算一段Python代码的耗时（腾讯）**


* **实现一个lambda表达式（字节跳动）**
  * [Lambda 表达式有何用处？如何使用？](https://www.zhihu.com/question/20125256)
* **用map/reduce实现数组求和（PayPal）**
  * map --> 将传入函数依次作用于序列中的每个元素，并把结果作为新的Iterator返回;
  * reduce --> 累积计算, 求和 ```reduce(lambda x, y : x + y, [1,2,3,4,5])```.
  * [map/reduce](https://www.liaoxuefeng.com/wiki/1016959663602400/1017329367486080)
* **描述Python的迭代器和生成器（DaoCloud）** 
  * [Python3 迭代器与生成器](https://www.runoob.com/python3/python3-iterator-generator.html) 



### Async IO

（这是个人Sharing的整理，夹带私货。）

* [python_asyncio_learning](https://github.com/KrisCheng/python_asyncio_learning)



## 数据库

### 基础问题

* **描述事务的隔离级别（野村证券/远景智能/网易/小红书）**
  * 经典面试题，一般八股过后还会追问MySQL（InnoDB）隔离级别的实现等等
  * Serializable（序列化） --> 可避免脏读，不可重复读，幻读
  * Repeatable read（可重复读） --> 可避免脏读，不可重复读，但可能出现幻读 
  * Read committed（已提交读） --> 可避免脏读，但是可能会造成不可重复读
  * Read uncommitted（未提交读） --> 级别最低，什么都避免不了（事务可以看到其他事务“尚未提交”的修改）
  * 脏读 --> 当一个事务允许读取另外一个事务修改但未提交的数据时，就可能发生 脏读
  * 不可重复度 --> 在一次事务中，当一行数据获取两遍得到不同的结果表示发生了 不可重复读
  * 幻读 --> 在事务执行过程中，当两个完全相同的查询语句执行得到不同的结果集。这种现象称为 幻读
  * [Transaction Isolation Levels](https://dev.mysql.com/doc/refman/8.0/en/innodb-transaction-isolation-levels.html)
  * [事务隔离 Wiki](https://zh.wikipedia.org/wiki/%E4%BA%8B%E5%8B%99%E9%9A%94%E9%9B%A2) 


* **delete、 drop、truncate 的区别（PayPal）**
  * drop --> 直接删掉表（不再需要一张表的时候，用drop）
  * truncate --> 删除的是表中的数据，再插入数据时自增长的数据id又重新从1开始（保留表而删除所有数据的时候用truncate，实际是删除原来的表并重建一张新表）
  * delete --> 删除表中数据，可以在后面添加where字句（想删除部分数据行时候，用delete，并且带上where子句）
  * [SQL truncate 、delete与drop区别](https://www.cnblogs.com/8765h/archive/2011/11/25/2374167.html)
* **第一/第三/BC范式，以及我们实际建表时为什么要设计冗余字段，同时设计冗余字段会带来什么问题（阿里）**
  * 区分快照 & 冗余
  * [数据库设计冗余字段问题？](https://www.zhihu.com/question/50662784)
  * [如何解释关系数据库的第一第二第三范式？](https://www.zhihu.com/question/24696366) 



### 索引

（面试常见八股（我真的怀疑有多少面试官实际有做过大规模的索引性能测试）。）

* **索引是什么，为什么MySQL使用B+树做索引（字节跳动/腾讯/美团/星环/网易）**
  * B+ 树做索引的优势
    * 相较AVL, 红黑树等二叉树，这些查找过程中要进行许多次的磁盘读取操作，非常耗时（逻辑结构上相近的节点在物理结构上可能会差很远），需要降低树的高度
    * 较 B树 的优势（字节跳动）
      * 相较于B树，B+每个**非叶子**节点存储的关键字数更多，树的层级更少所以查询数据更快（层级更少）
      * B+所有关键字数据地址都存在**叶子**节点上，所以每次查找的次数都相同所以查询速度要比B树更稳定（更稳定）
      * B+树所有的**叶子**节点数据构成了一个有序链表，在查询大小区间（范围查询）的数据时候更方便，数据紧密性很高，缓存的命中率也会比B树高（天然具有排序）
      * B+树遍历整棵树只需要遍历所有的**叶子**节点即可，而不需要像B树一样需要对每一层进行遍历，这有利于数据库做全表扫描
  * [为什么 MySQL 使用 B+Tree？](https://smartkeyerror.oss-cn-shenzhen.aliyuncs.com/Phyduck/database/%E4%B8%BA%E4%BB%80%E4%B9%88MySQL%E4%BD%BF%E7%94%A8B%2BTree.pdf)
  * [一步步分析为什么B+树适合作为索引的结构](https://blog.csdn.net/weixin_30531261/article/details/79312676)
  * [平衡二叉树、B树、B+树、B*树 理解其中一种你就都明白了](https://zhuanlan.zhihu.com/p/27700617)


* **聚集索引（Clustered Index）和非聚集索引的区别（拼多多/网易/字节跳动/Wish/携程）**
  * 聚集索引 --> 指数据库表行中数据的物理顺序与索引键值的逻辑顺序相同
  * 每个表只能有一个聚集索引，因为目录只能按照一种方法进行排序
  * [聚集索引与非聚集索引的总结](https://www.imooc.com/article/22915) 
  * [聚合索引(clustered index) / 非聚合索引(nonclustered index)](https://blog.csdn.net/ak913/article/details/8026743)
  * [快速理解聚集索引和非聚集索引](https://blog.csdn.net/zc474235918/article/details/50580639)
  * [聚集索引](https://baike.baidu.com/item/%E8%81%9A%E9%9B%86%E7%B4%A2%E5%BC%95) 


* **对于海量数据，如何提高查询效率（数据库优化策略）（野村证券）** 
  * [优化1——数据库优化面试题](https://blog.csdn.net/u010796790/article/details/52194850) 
* **一个本来很快的SQL突然效率变慢，如何排查原因（阿里）**
* **慢查询的优化思路（字节跳动）** 
* **给定常用SQL语句，如何建立索引（Shopee）**
  * 有A,B,C三个字段，常用SQL 语句为 `SELECT A,B,C where B=80 AND C > 200`, `SELECT A,B,C where A=50 AND B=80 AND C = 200`，如何建立索引



### SQL语句

（一些基本的SQL问题，有时也会碰到给定基本需求的写SQL题。）

* **SQL优化策略** 
  * [SQL优化2020最全干货总结---MySQL](https://developer.aliyun.com/article/779151)
  * [这大概是最全的sql优化方案了](https://zhuanlan.zhihu.com/p/48385127)	
* **having 和 where 用法上的区别（网易）**
  * [What is the difference between HAVING and WHERE in SQL?](https://stackoverflow.com/questions/287474/what-is-the-difference-between-having-and-where-in-sql) 
* **in 和 exists 的区别和使用场景（阿里）**
* **各种join操作的区别（left, right, inner join）** 
  * [mysql join操作](https://www.cnblogs.com/ggjucheng/archive/2012/11/06/2757972.html)



### MySQL

（国内互联网公司一般会从SQL问题过渡到MySQL问题（技术栈还是太单一了啊）。）

* **MySQL索引不命中（索引失效）的可能原因及策略（美团/腾讯）**  
  * [MySQL索引无法命中的几种情况及索引验证方法](http://www.chinacion.cn/article/4907.html) 
* **MySQL如何实现隔离级别的（如可重复读的实现原理）（拼多多/字节跳动）** 
  * MySQL Inno DB 默认隔离级别 --> 可重复读
  * MVCC（多版本并发控制）（Inno DB引擎实现）
  * [InnoDB---可重复读隔离级别的底层实现原理](https://blog.csdn.net/huanghanqian/article/details/79517480)
  * [MySQL事务隔离级别的实现原理](https://www.cnblogs.com/cjsblog/p/8365921.html)
  * [轻松理解MYSQL MVCC 实现机制](https://blog.csdn.net/whoamiyang/article/details/51901888)
* **MySQL联合索引命中情景分析（美团）**


* **InnoDB的索引结构（字节跳动）** 
* **MySQL常见的数据库引擎（网易）**
  * [Mysql四种常见数据库引擎](https://yq.aliyun.com/articles/636314) 
* **MySQL中如何使用和实现悲观锁和乐观锁（Shopee）**
* **MySQL有哪些常见的锁和具体的实现（百度）**
* **分库分表实践（百度）**



### MongoDB

（个人工作项目使用，但由于国内目前用得不是很多，没怎么碰到过实际面试题。）

* **项目中使用Mongo的优势**
  * 敏捷迭代，初期变化频繁
  * embedded document 场景匹配（表示包含关系，一对多，如Order等Model）
  * 弱一致性，保证了性能（对于Payment等场景还是需要使用支持事务的数据库）




## 操作系统

（计算机基础，八股重地，可以问得很深入（尤其字节跳动等非语言倾向公司）。）

* **进程/线程的概念和区别（字节跳动/拼多多）** 
  * 进程 --> 计算机中运行中的程序，具有一定独立功能的程序关于某个数据集合上的一次运行活动，进程是系统进行资源分配和调度的一个独立单位
  * 线程 --> 操作系统能够进行运算调度的最小单位，它被包含在进程之中，是进程中的实际运作单位
  * 进程和线程都是一个CPU工作时间段的描述，不过是颗粒大小不同。一个程序至少有一个进程，一个进程至少有一个线程
  * [线程和进程的区别是什么？](https://www.zhihu.com/question/25532384) 
  * [线程 Wiki](https://zh.wikipedia.org/wiki/%E7%BA%BF%E7%A8%8B) / [进程 Wiki](https://zh.wikipedia.org/wiki/%E8%A1%8C%E7%A8%8B)
  * [进程与线程的一个简单解释](http://www.ruanyifeng.com/blog/2013/04/processes_and_threads.html) （科普，类比：进程 -- 车间 / 线程 -- 车间里的工人）


* **线程同步（通信）的方式（字节跳动）**   
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
	* [Inter Process Communication (IPC) in OS](https://www.guru99.com/inter-process-communication-ipc.html)
	* [进程间8种通信方式详解](https://blog.csdn.net/violet_echo_0908/article/details/51201278) 
* **Java中start() 和 run() 方法的区别（字节跳动）** 

  * start() -- Creates a new thread and the run() method is executed on the newly created thread. (Can’t be invoked more than one time otherwise throws *java.lang.IllegalStateException*)
  * run() -- No new thread is created and the run() method is executed on the calling thread itself. (Multiple invocation is possible)
  * [Difference between Thread.start() and Thread.run() in Java](https://www.geeksforgeeks.org/difference-between-thread-start-and-thread-run-in-java/) 


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


* **kill掉一个进程（从指令输入开始），操作系统做了什么事情（字节跳动）**
* **描述分页&&分段存储（字节跳动）** 


* **什么是系统调用（爱奇艺）**
  * 指运行在用户空间的程序向操作系统内核请求需要更高权限运行的服务
  * linux内核中设置了一组用于实现系统功能的子程序，称为系统调用。系统调用和普通库函数调用非常相似，只是系统调用由操作系统核心提供，运行于**内核态**，而普通的函数调用由函数库或用户自己提供，运行于**用户态**
  * [系统调用 Wiki](https://zh.wikipedia.org/wiki/%E7%B3%BB%E7%BB%9F%E8%B0%83%E7%94%A8)
  * [Linux系统调用详解（实现机制分析）--linux内核剖析（六）](https://blog.csdn.net/gatieme/article/details/50779184)
  * [用户态和内核态的区别](https://blog.csdn.net/youngyoungla/article/details/53106671) 




## 计算机网络

（八股重地，可以问得非常深入，这是Web的基础。）

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


* **用Socket描述TCP的三次握手（腾讯）** 
	* [Socket过程详细解释（包括三次握手建立连接，四次握手断开连接）](https://blog.csdn.net/u013782203/article/details/51767763)（C++实现）


* **网络间的进程如何表示（腾讯）** 
	* [网络中进程之间如何通信](https://blog.csdn.net/bajiudongfeng/article/details/51568874) 
* **TCP和UDP的特点和区别，分别适用于什么场景（腾讯）**
	
	* TCP --> 面向连接 / UDP --> 无连接（发送数据前不需要建立连接）
	* TCP 提供可靠的服务（数据传输）/ UDP 无法保证
	* TCP --> 字节流 / UDP --> 数据报文段
	* [TCP和UDP的区别](https://zhuanlan.zhihu.com/p/24860273)
	* [常见面试题整理--计算机网络篇（每位开发者必备）](https://zhuanlan.zhihu.com/p/24001696)
	* [TCP vs UDP: Key Difference between TCP and UDP Protocol](https://www.guru99.com/tcp-vs-udp-understanding-the-difference.html)


* **TIME_WAIT状态产生（腾讯）** 
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
	* [What happens when...](https://github.com/alex/what-happens-when) （最全面的解释）
	* [从输入URL到页面加载发生了什么](https://segmentfault.com/a/1190000006879700)（依次逐步解释）
	 	* [在浏览器地址栏输入一个URL后回车，背后会进行哪些技术步骤？](https://www.zhihu.com/question/34873227)（更具体的解释）
	 	* [DNS递归查询和迭代查询的区别](https://blog.csdn.net/wuchuanpingstone/article/details/6720723)


* **DNS的过程（字节跳动）** 
* **HTTP 与 HTTPS 的区别（字节跳动）**  
  * HTTP协议以明文方式发送内容，不提供任何方式的数据加密
  * HTTPS其实就是建构在SSL（Secure Sockets Layer） / TLS之上的 HTTP协议
  * HTTPS密文传输 / HTTP 明文传输
  * HTTPS协议需要到CA申请证书
  * [详细解析 HTTP 与 HTTPS 的区别](https://juejin.im/entry/58d7635e5c497d0057fae036) 
  * [What Is the Difference Between HTTP and HTTPS?](https://www.keycdn.com/blog/difference-between-http-and-https)


* **描述HTTPS的加密过程（字节跳动）** 
* **对称加密&非对称加密在HTTPS加密过程中如何实践（字节跳动/阿里）** 
  * [HTTPS加密过程和TLS证书验证](https://juejin.im/post/5a4f4884518825732b19a3ce)
  * [HTTPS中的TLS](https://github.com/Snailclimb/JavaGuide/blob/master/docs/network/HTTPS%E4%B8%AD%E7%9A%84TLS.md)（密码学角度）
  * [How does HTTPS work? What's a CA? What's a self-signed Certificate?](https://www.youtube.com/watch?v=T4Df5_cojAs) （HTTPS工作流程举例）


* **HTTP代理如何实现（阿里）** 
	* [如何实现一个HTTP/HTTPS代理客户端 ](https://github.com/fwon/blog/issues/38)


* **描述SSO的原理（拼多多）** 
  * [CAS实现单点登录SSO执行原理探究(终于明白了)](https://blog.csdn.net/javaloveiphone/article/details/52439613)
  * [How does single sign-on work?](https://www.onelogin.com/learn/how-single-sign-on-works) 
* **网络拥塞的解决方案（字节跳动）** 

  * [网络拥塞成因与处理](https://blog.csdn.net/oZhuZhiYuan/article/details/52167246) 
* **描述Session的实现原理（或者如何设计一个Session）（拼多多）** 
* **如何保证token不被劫持和篡改（大概意思，项目相关）（微软）**   

* **业界有哪些网络认证的方法（基于设备认证项目提问）（阿里）** 

* **介绍 OSI 七层模型（蔚来）**
  * 应用层（应用层 --> 表示层 --> 会话层） --> 传输层 --> 网络层 --> 数据链路层 --> 物理层 (7层)
  * 应用层 --> 传输层 --> 网络层 --> 数据链路层 --> 物理层 （5层）
  * 并非标准，一个概念性框架
  * [OSI七层模型详解](https://blog.csdn.net/yaopeng_2005/article/details/7064869)
  * [干货：计算机网络知识总结.md](https://github.com/Snailclimb/JavaGuide/blob/master/docs/network/%E5%B9%B2%E8%B4%A7%EF%BC%9A%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%9F%A5%E8%AF%86%E6%80%BB%E7%BB%93.md#%E4%B8%80%E8%AE%A1%E7%AE%97%E6%9C%BA%E6%A6%82%E8%BF%B0)（逐层术语解释）



## Linux指令

（这部分可以平时工作做一些刻意练习，更多是个人意识问题。）

* cpu load 和 cpu utilization的区别（阿里）
* top，load 指令，free 中 cached和buffers的区别（阿里）
* 找出某目录下文件中带电子邮箱的文件（爱奇艺）
* 杀死所有Java进程
  * `ps -ef | grep java | grep -v grep | awk '{print $2}' | xargs kill -9`
  * [Linux 杀掉所有Java进程](https://blog.csdn.net/u011517841/article/details/79781830) 
* 干掉占用某端口的服务（网易）
  * [linux杀死占用某端口的所有进程](https://blog.csdn.net/lissdy/article/details/70256032)
* 打印一个文本中出现次数前十的数据（腾讯）




## 框架

（该部分罗列的都差不多是后端工程师的必修课了。每个框架应该秉承 1.解决什么问题 2.怎么解决的 3.实现细节 来逐一分析）

### Spring & SpringBoot

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
* **描述Spring的AOP（小红书/拼多多）** 
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
  * Spring AOP 具体实现（源码级别）
    * Java JDK 动态代理 （默认）
    * CGLIB 动态代理
  * 爱奇艺项目中AOP的实现（切面设计）（eBay）
    * @Before，判断模板有效性等
  * [关于 Spring AOP (AspectJ) 你该知晓的一切](https://blog.csdn.net/javazejian/article/details/56267036)（AOP入门 + 应用场景 + Spring中的基本实现）
  * [《Spring设计思想》AOP设计基本原理](https://blog.csdn.net/luanlouis/article/details/51095702)（从程序运行角度解释AOP的工作原理）
  * 《Spring实战（第四版）》第四章
  * [Spring AOP就是这么简单啦](https://juejin.im/post/5b06bf2df265da0de2574ee1)（可在面试前看的纯干货）
  * [《Spring设计思想》AOP实现原理（基于JDK和基于CGLIB）](https://blog.csdn.net/luanlouis/article/details/51155821) （Spring AOP的完整实现过程）
* **什么是Spring注解，Spring中有哪些常用的注解，以及注解自身是如何实现的（阿里/字节跳动）** 
  * 注解 --> 减少配置文件内容
  * [Java annotation Wiki](https://en.wikipedia.org/wiki/Java_annotation)
  * [秒懂，Java 注解 （Annotation）你可以这样学](https://blog.csdn.net/briblue/article/details/73824058)（简单理解： 注解 --> 标签）
  * [精进Spring—Spring常用注解](https://blog.csdn.net/u010648555/article/details/76299467)（常见注解）
* **描述Spring的IoC（拼多多）**
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
  * 源码阅读问题（星环）
  * [IoC-spring 的灵魂(带你轻松理解IOC思想及bean对象的生成过程)](https://juejin.im/post/593386ca2f301e00584f8036)（基本概念）
  * [【第二章】 IoC 之 2.1 IoC基础 ——跟我学Spring3](https://jinnianshilongnian.iteye.com/blog/1413846)（IoC思想详解）
  * [Spring IoC有什么好处呢？](https://www.zhihu.com/question/23277575/answer/169698662)（汽车的例子有助于理解IoC）
  * [Inversion of Control Containers and the Dependency Injection pattern](https://martinfowler.com/articles/injection.html)（Martin文章）
  * [Spring IOC 容器源码分析](https://javadoop.com/post/spring-ioc)（源码阅读）
  * [What is difference between BeanFactory and ApplicationContext in Spring framework](https://javarevisited.blogspot.com/2012/11/difference-between-beanfactory-vs-applicationcontext-spring-framework.html)


* **描述一个Spring Boot项目的启动过程（阿里）**
  * @SpringBootApplication --> 复合注解（@SpringBootConfiguration / @EnableAutoConfiguration / @ComponentScan）
  * [SpringBoot 应用程序启动过程探秘](https://juejin.im/post/5b8f05a5f265da43296c6102)


* **什么是JPA**
  * [Java持久化API Wiki](https://zh.wikipedia.org/wiki/Java%E6%8C%81%E4%B9%85%E5%8C%96API)
* **简述Spring Boot框架**
  * 核心
    * 自动配置
    * 起步依赖
  * 从本质上来说，Spring Boot就是Spring，它做了那些没有它你自己也会去做的Spring Bean配置
  * 《Spring Boot实战》前三章



### Redis 

(缓存基本是后端基本问题了，可惜个人当前实战经验不够，TBD)

* **缓存穿透(penetration)/击穿(breakdown)/雪崩(avalanche)（Shopee）**
  * [What are redis cache penetration, cache breakdown and cache avalanche?](https://cdmana.com/2021/01/20210117114056733b.html)

* **缓存一致性问题怎么解决（Shopee）**



### Elasticsearch 

* **ES的索引是怎么实现的（爱奇艺）**
* **项目中ES是如何使用的（Soul）**



### Kafka

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



### Netty

（TBD）



## Android && Frontend

个人有一些Android和 前端 的经验，但无奈后续没有深入了，这里简单提一嘴。

对于前端，一般会有 打包过程，框架（Vue.js），JS语法（回调，异步）等问题。

对于Android，会涉及 关键类，App生命周期，主要组件，AIDL通讯，回调 等内容，以及 App 性能优化等问题。




## 其他

（本部分罗列一些计算机基本问题，一般都比较简单。）

* **git rebase 和 git merge 有什么区别（小红书/野村证券/PayPal）**
  * 同：都是用于从一个分支获取并且合并到当前分支
  * 异：rebase --> 会合并之前的commit历史（带有破坏性的修改 commit 历史的命令）
  * 一个干净的，没有merge commit的线性历史树 --> git rebase
  * 保留完整的历史记录，并且想要避免重写commit history的风险 --> git merge
  * [git rebase 和 git merge 的区别](https://www.jianshu.com/p/f23f72251abc) 

* **浅拷贝 & 深拷贝（字节跳动）**
  * 浅拷贝 --> 对基本数据类型进行值传递，对引用数据类型进行引用传递般的拷贝，**没有真实的创建一个新的对象**
  * 深拷贝 --> 对基本数据类型进行值传递，对引用数据类型，**创建一个新的对象**，并复制其内容
  * [细说 Java 的深拷贝和浅拷贝](https://segmentfault.com/a/1190000010648514) 
  * [8.6: Pass by Value vs. Pass by Reference - Processing Tutorial](https://www.youtube.com/watch?v=hNR6fsksEu8)


* **git fetch 和 git pull 有什么区别（PayPal）**
  * pull = fetch + merge
  * [详解git fetch与git pull的区别](https://blog.csdn.net/riddle1981/article/details/74938111) 
* **值传递 & 引用传递**
  * Java中方法参数传递方式是按**值传递**
  * 如果参数是基本类型，传递的是基本类型的字面量值的拷贝
  * 如果参数是引用类型，传递的是该参量所引用的对象在堆中地址值的拷贝
  * [什么是值传递和引用传递？](https://www.zhihu.com/question/31203609/answer/50992895) 

