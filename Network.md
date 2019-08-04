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
		* 发送端 --> FIN (客户端进入FIN-WAIT-1（终止等待1）状态) 
		* 接收端 --> ACK (客户端收到服务器的确认请求后，此时，客户端就进入FIN-WAIT-2（终止等待2）状态) 
		* 接收端 --> FIN 
		* 发送端 --> ACK
	* [TCP的三次握手与四次挥手（详解+动图）](https://blog.csdn.net/qzcsu/article/details/72861891)

	
* **用Socket描述TCP的三次握手（腾讯）** *`TODO`* 
	* [Socket过程详细解释（包括三次握手建立连接，四次握手断开连接）](https://blog.csdn.net/u013782203/article/details/51767763)（C++实现，未看）


* **网络间的进程如何表示（腾讯）** *`TODO`* 
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


* **HTTP 与 HTTPS 的区别** 
	* HTTP协议以明文方式发送内容，不提供任何方式的数据加密
	* HTTPS其实就是建构在SSL（Secure Sockets Layer） / TLS之上的 HTTP协议
	* [详细解析 HTTP 与 HTTPS 的区别](https://juejin.im/entry/58d7635e5c497d0057fae036) 


* **描述HTTPS的加密过程（头条）** *`TODO`* 
	* [HTTPS加密过程和TLS证书验证](https://juejin.im/post/5a4f4884518825732b19a3ce)


* **HTTP代理如何实现（阿里）** *`TODO`* 
	* [如何实现一个HTTP/HTTPS代理客户端 ](https://github.com/fwon/blog/issues/38)


* 描述SSO的原理（拼多多）*`TODO`*


* 描述Session的实现原理（或者如何设计一个Session）（拼多多）*`TODO`*