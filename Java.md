### Spring 相关

* **描述Spring的IoC**
	* IoC是一种思想，并非一个具体技术
		* 基于 **依赖倒置原则（Dependency Inversion Principle）**
			* 把原本的高层建筑依赖底层建筑“倒置”过来，变成底层建筑依赖高层建筑。高层建筑决定需要什么，底层去实现这样的需求，但是高层并不用管底层是怎么实现的。这样就不会出现前面的“牵一发动全身”的情况。
		* 将原本在程序中手动创建对象的控制权，交由Spring框架来管理
		* 反转 --> 由 **IoC容器** 来帮忙创建及注入依赖对象
		* 实现 --> 依赖注入（相对 IoC 而言，“依赖注入” 明确描述了 “被注入对象依赖IoC容器配置依赖对象”）
	* 依赖注入，就是 **把底层类作为参数传入上层类，实现上层类对下层类的“控制”**
		* 谁依赖于谁：当然是应用程序依赖于IoC容器
		* 为什么需要依赖：应用程序需要IoC容器来提供对象需要的外部资源
		* 谁注入谁：很明显是IoC容器注入应用程序某个对象，应用程序依赖的对象
		* 注入了什么：就是注入某个对象所需要的外部资源（包括对象、资源、常量数据）
	* 好处
		* 让你脱离对依赖对象的维护，只需要随用随取，不需要关心依赖对象的任何过程
		* 可以有效地改善模块之间的紧耦合问题
	* [IoC-spring 的灵魂(带你轻松理解IOC思想及bean对象的生成过程)](https://juejin.im/post/593386ca2f301e00584f8036)
	* [【第二章】 IoC 之 2.1 IoC基础 ——跟我学Spring3](https://jinnianshilongnian.iteye.com/blog/1413846)
	* [Spring IoC有什么好处呢？](https://www.zhihu.com/question/23277575/answer/169698662)（汽车的例子有助于理解IoC）
	* [Inversion of Control Containers and the Dependency Injection pattern](https://martinfowler.com/articles/injection.html)（Martin文章 *`TODO`*）
	* [Spring IOC 容器源码分析](https://javadoop.com/post/spring-ioc)（源码阅读 *`TODO`*）


* **什么是Bean**
	* 在 Spring 中，构成应用程序主干并由Spring IoC容器管理的对象称为Bean。一个Bean是一个由Spring IoC容器实例化、组装和管理的对象
	* [第37讲 | 谈谈Spring Bean的生命周期和作用域？](https://time.geekbang.org/column/article/12472)
	* [Spring Bean是什么？](https://www.awaimai.com/2596.html)

	
* **描述Spring的AOP（小红书）**
	* AOP的理念
		* 将分散在各个业务逻辑代码中 相同的代码 通过 **横向切割** 的方式抽取到一个独立的模块中（模块化）
		* 将相同逻辑的重复代码横向抽取出来，使用动态代理技术将这些重复代码织入到目标对象方法中，实现和原来一样的功能。
	* 基本概念
		* 通知（advice） --> 切面的工作被称为通知，定义了切面是什么以及何时被使用
		* 连接点（join point） --> 应用执行过程中能够插入切面的一个点，可以是方法调用时，抛出异常时等等...
		* 切点（pointcut） --> 需要应用切面的方法（具体定位的连接点）
		* 切面（aspect） --> 切面是 通知 和 切点 的结合，共同定义：是什么，在何时和何处完成其功能
		* 织入(weaving) --> 把切面应用到目标函数的过程
	* 好处
		* 显示地声明在何处如何应用该行为，有效减少代码冗余，让类更加关注自身主要功能
	* Spring AOP 实现 *`TODO`*
		* Java JDK 动态代理
		* CGLIB 动态代理
	* [关于 Spring AOP (AspectJ) 你该知晓的一切](https://blog.csdn.net/javazejian/article/details/56267036)（AOP入门 + 应用场景 + Spring中的基本实现）
	* [《Spring设计思想》AOP设计基本原理](https://blog.csdn.net/luanlouis/article/details/51095702)（从程序运行角度解释AOP的工作原理）
	* [《Spring设计思想》AOP实现原理（基于JDK和基于CGLIB）](https://blog.csdn.net/luanlouis/article/details/51155821) （Spring AOP的完整实现过程 *`TODO`*）
	* 《Spring实战（第四版）》第四章
	* [Spring AOP就是这么简单啦](https://juejin.im/post/5b06bf2df265da0de2574ee1)（可在面试前看的纯干货）


* **简述Spring Boot框架**
	* 核心
		* 自动配置
		* 起步依赖
	* 从本质上来说，Spring Boot就是Spring，它做了那些没有它你自己也会去做的Spring Bean配置
	* 《Spring Boot实战》前三章


* **什么是JPA**
	* [Java持久化API Wiki](https://zh.wikipedia.org/wiki/Java%E6%8C%81%E4%B9%85%E5%8C%96API)


* **什么是Spring注解，以及Spring中有哪些常用的注解（阿里）**
	* 注解 --> 减少配置文件内容
	* [Java annotation Wiki](https://en.wikipedia.org/wiki/Java_annotation)
	* [秒懂，Java 注解 （Annotation）你可以这样学](https://blog.csdn.net/briblue/article/details/73824058)（简单理解： 注解 --> 标签）
	* [精进Spring—Spring常用注解](https://blog.csdn.net/u010648555/article/details/76299467)（常见注解）


### Java语法相关
	
* **字符串相关问题**
	* StringBuffer --> 线程安全 
	* StringBuilder --> 非线程安全
	* [第5讲 | String、StringBuffer、StringBuilder有什么区别？](https://time.geekbang.org/column/article/7349)


* **什么是序列化（Serialization）和反序列化（小红书）**
	* 序列化 --> 把对象转换为**字节序列**的过程称为对象的序列化
	* 反序列化 --> 把字节序列恢复为对象的过程称为对象的反序列化
	* [Java对象的序列化（Serialization）和反序列化详解](https://blog.csdn.net/yaomingyang/article/details/79321939)
	* [Java 之 Serializable 序列化和反序列化的概念,作用的通俗易懂的解释](https://blog.csdn.net/qq_27093465/article/details/78544505)

	
* **Java中父类和子类初始化顺序（小红书）**
	* 优先级排序
		* 1. 父类中静态成员变量和静态代码块
		* 2. 子类中静态成员变量和静态代码块
		* 3. 父类中普通成员变量和代码块，父类的构造函数
		* 4. 子类中普通成员变量和代码块，子类的构造函数
		* (其中“和”字两端的按照代码先后顺序执行)
	* [java中父类和子类初始化顺序](https://blog.csdn.net/yuxin6866/article/details/53107578) 


* **什么是反射以及反射有什么具体应用**
	* Java反射机制是在运行状态中，对于任意一个类，都能够知道这个类的所有属性和方法；对于任意一个对象，都能够调用它的任意一个方法和属性。这种 **动态获取的信息以及动态调用对象的方法的功能** 称为Java语言的反射机制
	* 应用
		* 框架设计的灵魂 --> 如：Spring 通过 XML 配置模式装载 Bean 的过程
		* 使用JDBC连接数据库时使用Class.forName()通过反射加载数据库的驱动程序
	* [什么是反射机制？反射机制的应用场景有哪些？](https://github.com/Snailclimb/JavaGuide/blob/master/docs/essential-content-for-interview/MostCommonJavaInterviewQuestions/%E7%AC%AC%E4%BA%8C%E5%91%A8(2018-8-13).md#%E4%BB%80%E4%B9%88%E6%98%AF%E5%8F%8D%E5%B0%84%E6%9C%BA%E5%88%B6%E5%8F%8D%E5%B0%84%E6%9C%BA%E5%88%B6%E7%9A%84%E5%BA%94%E7%94%A8%E5%9C%BA%E6%99%AF%E6%9C%89%E5%93%AA%E4%BA%9B)

	
* **Java提供了哪些IO方式（拼多多）**
	* 
	* []()


### 集合框架
		
* **HashMap 和 TreeMap 的区别（PayPal）**
	* HashMap通过hashcode对其内容进行快速查找，而 TreeMap 中所有的元素都保持着某种固定的顺序，如果你需要得到一个有序的结果你就应该使用TreeMap（HashMap中元素的排列顺序是不固定的）
	* HashMap 允许使用 null 值和 null 键，而 TreeMap 不可以
	* 实现
		* HashMap --> HashMap实际上是一个“链表散列”的数据结构，即数组和链表的结合体；如果追加节点后，链表数量 >= 8，则转化为红黑树
		* TreeMap --> 红黑树
	* HashMap 非线程安全 & TreeMap 非线程安全
	* [HashMap和TreeMap区别详解以及底层实现](https://blog.csdn.net/xlgen157387/article/details/47907721)
	* [第9讲 | 对比Hashtable、HashMap、TreeMap有什么不同？](https://time.geekbang.org/column/article/8053)

	
* **描述 HashMap 的底层实现（远景智能）**
	* 解决哈希冲突
		* JDK < 1.8 --> 数组和链表
		* JDK >= 1.8 --> 链表长度大于阈值（默认为8）时，将链表转化为红黑树，以减少搜索时间
	* 源码
		* get()
		* put() 
		* capacity --> buckets的数目 / load factor (负载因子) --> buckets填满程度的最大比例
	* [HashMap 简介](https://github.com/Snailclimb/JavaGuide/blob/master/docs/java/collection/HashMap.md)
	* [使用HashMap，如果key是自定义的类，就必须重写hashcode()和equals()](https://blog.csdn.net/tuolaji8/article/details/48417031)


* **HashSet 如何判断重复元素（小红书）**
	* 首先会调用 Object 的 hashCode 方法判 hashCode 是否已经存在，如不存在则直接插入元素
	* 如果已存在则调用 Object 对象的 equals 方法判断是否返回true， 如果为true则说明元素已经存在，如为false则插入元素
	* Java对象的 eqauls 方法和 hashCode 方法是这样规定的：
		* 1. 相等（相同）的对象必须具有相等的哈希码（或者散列码）
		* 2. 如果两个对象的hashCode相同，它们并不一定相同
	* [HashSet重复元素判断](https://itfafa.iteye.com/blog/1698690) 
	* [Java提高篇——equals()与hashCode()方法详解](https://www.cnblogs.com/Qian123/p/5703507.html)


### Java内存模型
	
* **描述Java内存模型（阿里）**
	* JVM内存区域划分
		* 程序计数器（PC, Program Counter Register） --> 它的作用可以看做是当前线程所执行的字节码的行号指示器
		* 虚拟机栈（Virtual Machine Stack） --> 保存一个个栈帧（Stack Frame），对应着一次次的Java **方法调用**
		* 本地方法栈（Native Method Stack） --> 和虚拟机栈类似，区别为虚拟机栈为虚拟机执行Java方法（也就是字节码）服务，而本地方法栈为虚拟机使用到的Native方法服务
		
			⬆️（线程私有）--- （线程共享） ⬇️
		
		* 堆（Heap） --> 所有线程共享的内存区域，几乎所有的 **对象实例** 都在这里分配内存
		* 方法区（Method Area） --> 所有线程共享的一块内存区域，用于存储所谓的元（Meta）数据，如类结构信息，以及对应的运行时常量池、字段、方法代码等
		* 运行时常量池（Run-Time Constant Pool） --> 属于方法区的一部分，存放各种常量信息
	* [第25讲 | 谈谈JVM内存区域的划分，哪些区域可能发生OutOfMemoryError?](https://time.geekbang.org/column/article/10192)
	* [Java 内存区域详解](https://github.com/Snailclimb/JavaGuide/blob/master/docs/java/jvm/Java%E5%86%85%E5%AD%98%E5%8C%BA%E5%9F%9F.md)


* **描述Java的GC过程（DaoCloud）**
	* 对象存活判断
		* 引用计数（Python 的 GC），无法解决对象相互循环引用的问题，Java中没有使用（Python GC有应用）
		* 可达性分析（GC Roots --> 虚拟机栈和本地方法栈中正在引用的对象、静态属性引用的对象和常量）
	* 垃圾收集算法
		* 标记-清除算法（Mark-Sweep） --> 内存碎片化问题
		* 复制算法（Copying） --> 将内存分为大小相同的两块，每次使用其中的一块。每次将活着的对象复制到 to 区域，拷贝过程中将对象顺序放置，避免内存碎片化
		* 标记-整理算法（Mark-Compact） --> 类似于标记-清除，但为了避免内存碎片化，**在清理过程中移动对象，以确保移动后的对象占用连续的内存空间**
		* 分代收集算法 --> 根据对象存活周期的不同将内存分为几块(eg: 新生代/老生代)
	* [第27讲 | Java常见的垃圾收集器有哪些？](https://time.geekbang.org/column/article/10513)
	* [jvm系列(三):GC算法 垃圾收集器](https://mp.weixin.qq.com/s?__biz=MzI4NDY5Mjc1Mg==&mid=2247483952&idx=1&sn=ea12792a9b7c67baddfaf425d8272d33&chksm=ebf6da4fdc815359869107a4acd15538b3596ba006b4005b216688b69372650dbd18c0184643&scene=21#wechat_redirect)
	* [JVM 垃圾回收](https://github.com/Snailclimb/JavaGuide/blob/master/docs/java/jvm/JVM%E5%9E%83%E5%9C%BE%E5%9B%9E%E6%94%B6.md)


* **浅拷贝 & 深拷贝（头条）**
	* 浅拷贝 --> 对基本数据类型进行值传递，对引用数据类型进行引用传递般的拷贝，没有真实的创建一个新的对象
	* 深拷贝 --> 对基本数据类型进行值传递，对引用数据类型，创建一个新的对象，并复制其内容
	* [细说 Java 的深拷贝和浅拷贝](https://segmentfault.com/a/1190000010648514) 
	* [8.6: Pass by Value vs. Pass by Reference - Processing Tutorial](https://www.youtube.com/watch?v=hNR6fsksEu8)
	

* **值传递 & 引用传递**
	* Java中方法参数传递方式是按**值传递**
	* 如果参数是基本类型，传递的是基本类型的字面量值的拷贝
	* 如果参数是引用类型，传递的是该参量所引用的对象在堆中地址值的拷贝
	* [什么是值传递和引用传递？](https://www.zhihu.com/question/31203609/answer/50992895) 
	
	
### Java并发编程 *`TODO`*

* **描述Java下的并发编程（阿里）**
	* 线程的生命周期（新建 / 就绪 / 运行 / 阻塞 / 死亡）
	* 创建线程的方法（Runnable接口 / 继承Thread / 通过 Callable 和 Future 创建线程）
	* [Java 多线程编程](https://www.runoob.com/java/java-multithreading.html)

		
* **什么是线程安全**
	* 指某个函数、函数库在多线程环境中被调用时，能够正确地处理多个线程之间的共享变量，使程序功能正确完成
	* a class is thread safe when it continues to behave correctly when accessed from multiple threads
	* [线程安全 Wiki](https://zh.wikipedia.org/wiki/%E7%BA%BF%E7%A8%8B%E5%AE%89%E5%85%A8)
	
	
* **sychronized 和 ReentrantLock**
	* synchronized 锁住的是括号里的对象，而不是代码
	* 可重入 --> 当一个线程试图获取一个它已经获取的锁时，这个获取动作就自动成功（自己可以再次获取自己的内部锁）
	* [Java线程同步：synchronized锁住的是代码还是对象](https://blog.csdn.net/xiao__gui/article/details/8188833) 
	* [第15讲 | synchronized和ReentrantLock有什么区别呢？](https://time.geekbang.org/column/article/8799)


* **volatile**
	* 保证变量的可见性（指示 JVM，这个变量是不稳定的，每次使用它都到主存中进行读取） & 防止指令重排序
	* 只能用于变量
	* [2. volatile关键字](https://github.com/Snailclimb/JavaGuide/blob/master/docs/java/Multithread/JavaConcurrencyAdvancedCommonInterviewQuestions.md#2-volatile%E5%85%B3%E9%94%AE%E5%AD%97)

	
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


* **乐观锁与悲观锁的概念，常见实现（阿里）**
	* 乐观锁适用于**多读**的应用类型，这样可以提高吞吐量 / 悲观锁适合于**多写**
	* 乐观锁常见实现 --> 版本号机制 / CAS 算法
		* CAS 算法概念 / 缺点
			* ABA 问题
	* [何谓悲观锁与乐观锁](https://github.com/Snailclimb/JavaGuide/blob/master/docs/essential-content-for-interview/%E9%9D%A2%E8%AF%95%E5%BF%85%E5%A4%87%E4%B9%8B%E4%B9%90%E8%A7%82%E9%94%81%E4%B8%8E%E6%82%B2%E8%A7%82%E9%94%81.md)
	* [Compare-and-swap Wiki](https://en.wikipedia.org/wiki/Compare-and-swap)


* **join() 方法有什么用**
	* Thread.join() 把指定的线程加入到当前线程，可以将两个交替执行的线程合并为顺序执行的线程。比如在线程B中调用了线程A的join()方法，直到线程A执行完毕后，才会继续执行线程B
	* [Java多线程中join方法的理解](https://uule.iteye.com/blog/1101994)
	* [简谈Java的join()方法](https://www.cnblogs.com/techyc/p/3286678.html) 

	
* **其他并发学习资源**
	* [面向面试的Java并发基础整理](http://pengcheng.tech/2019/03/24/%e9%9d%a2%e5%90%91%e9%9d%a2%e8%af%95%e7%9a%84java%e5%b9%b6%e5%8f%91%e5%9f%ba%e7%a1%80%e6%95%b4%e7%90%86/) （个人初步总结，发现还是应付不了面试Orz...）
	* [Java并发编程学习路线](https://zhuanlan.zhihu.com/p/25577863)（学习思路篇）
	* [Java Concurrency in Practice](https://book.douban.com/subject/1888733/)（*`TODO`* 请直接抛弃中文版，翻译极其垃圾，但原版对初学者不是很友好，不是很好懂）
	* [Java并发编程实战](https://time.geekbang.org/column/intro/159)(*`TODO`* 极客时间课程)
