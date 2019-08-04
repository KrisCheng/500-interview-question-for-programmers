* **常见Linux指令** *`TODO`*

    * top，load 指令，free 中 cached和buffers的区别（阿里）
  * 找出某目录下文件中带电子邮箱的文件（爱奇艺）

* **git rebase 和 git merge 有什么区别（小红书/野村证券/PayPal）**
	* 同：都是用于从一个分支获取并且合并到当前分支
	* 异：rebase --> 会合并之前的commit历史（带有破坏性的修改 commit 历史的命令）
	* 一个干净的，没有merge commit的线性历史树 --> git rebase
	* 保留完整的历史记录，并且想要避免重写commit history的风险 --> git merge
	* [git rebase 和 git merge 的区别](https://www.jianshu.com/p/f23f72251abc) 
 

* **git fetch 和 git pull 有什么区别（PayPal）**
	* pull = fetch + merge
	* [详解git fetch与git pull的区别](https://blog.csdn.net/riddle1981/article/details/74938111)


* 描述 git 中的 cherry-pick 指令（小红书）*`TODO`* 


* sqrt()是如何实现的（拼多多）*`TODO`* 