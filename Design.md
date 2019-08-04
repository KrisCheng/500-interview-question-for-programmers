### 设计模式

* **简述设计模式**
	* 创建型 / 结构型 / 行为型
	* [第14讲 | 谈谈你知道的设计模式？](https://time.geekbang.org/column/article/8624)

	 
* **实现一个线程安全的单例模式**
	* 懒汉模式 --> Lazy初始化
	* 饿汉模式 --> 在方法调用前，实例就已经创建好了
	* 全部 sychronized 锁住 --> 可以保证线程安全，但销效率低
	* “双重检查锁”机制版本 （面试用这个）
		* volatile 来保证其线程间的可见性，禁止指令重排
		* 同步代码块中使用二次检查，以保证其不被重复实例化
	* 枚举enum和静态代码块的特性相似，在使用枚举时，构造方法会被自动调用，利用这一特性也可以实现单例（面试可稍微提及）
	* [高并发下线程安全的单例模式（最全最经典）](https://blog.csdn.net/cselmu9/article/details/51366946) （单例的N种实现）
	* [单例模式](https://www.runoob.com/design-pattern/singleton-pattern.html)（详尽介绍）


### 设计/架构

* 描述MVVM思想（拼多多）


### 场景题

* 高并发访问下如何保证用户名行为不冲突，比如多个用户同时创建同一个用户名（拼多多）*`TODO`* 


* 一个任务序列执行顺序如 A --> B1,B2,B3 --> C，如何保证该任务执行先后顺序的准确性（拼多多）*`TODO`* 
	* CountDownLatch 


* **如何设计一个秒杀系统（小红书）** *`TODO`* 
	* [Java开发面试：高并发秒杀系统如何设计与优化](https://blog.csdn.net/CSDN_Terence/article/details/77744042)
	* [如何设计一个秒杀系统](https://blog.csdn.net/suifeng3051/article/details/52607544)


* **设计一个方案，提供不同算法调用接口（参数即为需要调用的方法名）（设计模式实际应用）（PayPal）**
	* 这题感觉非常开放，我当时答了用 适配器模式，似乎面试官并不是特别满意
	* 适配器模式 应该是可以的
	* 工厂模式(定义一个创建对象的接口，让其子类自己决定实例化哪一个工厂类，工厂模式使其创建过程延迟到子类进行。) 应该也可以 --> 传入方法参数，实例化具体对象
	* [两道设计模式的面试题](https://www.cnblogs.com/Binhua-Liu/archive/2010/12/23/1914935.html)
	* [工厂模式](https://www.runoob.com/design-pattern/factory-pattern.html)