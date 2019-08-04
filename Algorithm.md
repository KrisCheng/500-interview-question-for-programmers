### 排序相关

* **（TopK 问题）给定一个无符号，包含10亿个数的数组，如何取出前100大个数（头条/腾讯）**
	* 答题思路
		* 全局排序 O(nlogn)
		* 冒泡（k个）O(kn)
		* 堆排 O(nlogk)
			* 建立一个容量为k的大/小顶堆
			* n个元素逐一比较，O(logk) 完成删除和插入操作
	* 询问资源 --> 内存 / 核数 / 单机or多机，MapReduce思想
	* [最小的K个数](https://www.nowcoder.com/practice/6a296eb82cf844ca8539b57c23e6e9bf?tpId=13&tqId=11182&rp=1&ru=/ta/coding-interviews&qru=/ta/coding-interviews/question-ranking)
	* [海量数据处理 - 10亿个数中找出最大的10000个数（top K问题）](https://blog.csdn.net/zyq522376829/article/details/47686867) 


* **如何找到一个无序数组的中位数**
	* 快排 or 堆排思想
	* [找出一个无序数组的中位数](https://blog.csdn.net/oneday_789/article/details/76681764) 


* **如何给一个很大的无序数组去重（腾讯）**
	* 哈希分流 + 去重
	* 排序 + 扫描一遍去重
	* [26. 删除排序数组中的重复项](https://leetcode-cn.com/problems/remove-duplicates-from-sorted-array/)


* **Java自带的 sort() 方法是如何实现的（阿里）**
	* DualPivotQuicksort（双轴快速排序）
	* [Collections.sort()和Arrays.sort()排序算法选择](https://blog.csdn.net/TimHeath/article/details/68930482)


* **手写主流排序算法 & 复杂度/稳定性分析（腾讯/头条/阿里/蜻蜓FM）**
	* 稳定排序 --> 冒泡排序、插入排序、归并排序
	* 不稳定排序 --> 快速排序、希尔排序、选择排序、堆排序
	* 常见问法
		* 手写快排/堆排
		* 快排复杂度分析（最好/最坏/平均） / 建堆的复杂度分析 O(N)
		* 归并排序的Top-Down & Bottom-up
	* [7种经典排序算法及实现](http://pengcheng.tech/2019/03/04/%e7%bb%8f%e5%85%b8%e6%8e%92%e5%ba%8f%e7%ae%97%e6%b3%95%e5%8f%8a%e5%ae%9e%e7%8e%b0%e6%8c%87%e5%8d%97/)
	* [排序算法稳定性](https://baike.baidu.com/item/%E6%8E%92%E5%BA%8F%E7%AE%97%E6%B3%95%E7%A8%B3%E5%AE%9A%E6%80%A7)
	* [排序算法可视化](https://visualgo.net/en/sorting)
	* [快排 Wiki](https://zh.wikipedia.org/zh/%E5%BF%AB%E9%80%9F%E6%8E%92%E5%BA%8F)
	* [堆排 Wiki](https://zh.wikipedia.org/wiki/%E5%A0%86%E6%8E%92%E5%BA%8F)（*`TODO`* 堆排的实现）
	* [归并排序 Wiki](https://zh.wikipedia.org/wiki/%E5%BD%92%E5%B9%B6%E6%8E%92%E5%BA%8F)（*`TODO`* 递归版本和循环版本的实现）


* **数组中的逆序对**
	* 归并排序 && 递归的应用
	* 引入中间数组临时存放排序数据
	* [数组中的逆序对](https://www.nowcoder.com/practice/96bd6684e04a44eb80e6a68efc0ec6c5?tpId=13&tqId=11188&rp=1&ru=/ta/coding-interviews&qru=/ta/coding-interviews/question-ranking) 


### 树

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


* **非递归从左至右打印一颗二叉树中的所有路径（拼多多）**
	* [257. 二叉树的所有路径](https://leetcode-cn.com/problems/binary-tree-paths/) 


* **将二叉搜索树转化成一个排序的双向链表**
	* [二叉搜索树与双向链表](https://www.nowcoder.com/practice/947f6eb80d944a84850b0538bf0ec3a5?tpId=13&tqId=11179&rp=1&ru=/ta/coding-interviews&qru=/ta/coding-interviews/question-ranking)
 

* **红黑树描述及其复杂度分析（插入/查找）（腾讯/阿里）** *`TODO`*
	* 查找、插入、删除 -- logn
	* [红黑树 Wiki](https://zh.wikipedia.org/wiki/%E7%BA%A2%E9%BB%91%E6%A0%91) 


* 如何将一棵非平衡二叉树转化成平衡二叉树（HyperS） *`TODO`* 


### 链表/数组/栈/队列

* **反转链表（小红书/腾讯）**
	* [206. 反转链表](https://leetcode-cn.com/problems/reverse-linked-list/) 

	
* **复杂链表的复制**
	* 连接一个重复链表
	* 断链，拆分成两个链表（清楚断链的操作是什么）
	* [复杂链表的复制](https://www.nowcoder.com/practice/f836b2c43afc4b35ad6adc41ec941dba?tpId=13&tqId=11178&rp=1&ru=/ta/coding-interviews&qru=/ta/coding-interviews/question-ranking) 

	
### 字符串

* **如何找出一个字符串中的最大不重复子串（蜻蜓FM）**
	* 暴力求解 --> 逐个遍历，找最长子串（设置一个 allUnique 函数）/ O(n^3)
	* 滑动窗口 --> 滑动窗口至到最后一个元素，每当碰到重复左指针往后走，否则右指针往后走，同时比较 / O(n)
	* [3. 无重复字符的最长子串](https://leetcode-cn.com/problems/longest-substring-without-repeating-characters/solution/wu-zhong-fu-zi-fu-de-zui-chang-zi-chuan-by-leetcod/)


* **字符串的排列**
	* 理解递归结构的构造过程（固定一个字符，继续处理剩余字符）
	* 是对一个确定的初始字符串进行操作，得到一个结果后通过需要换回来
	* [字符串的排列](https://www.nowcoder.com/practice/fe6b651b66ae47d7acce78ffdd9a96c7?tpId=13&tqId=11180&rp=1&ru=/ta/coding-interviews&qru=/ta/coding-interviews/question-ranking) 


### 动态规划

* **描述背包问题（HyperS）**
	* [背包问题 Wiki](https://zh.wikipedia.org/wiki/%E8%83%8C%E5%8C%85%E9%97%AE%E9%A2%98) 


### 其他

* **买卖股票的最佳时机（野村证券/头条）**
	* [121. 买卖股票的最佳时机](https://leetcode-cn.com/problems/best-time-to-buy-and-sell-stock/) 


* **斐波那契数列的尾递归实现（Wish）**
	* 尾递归就是把当前的运算结果（或路径）放在参数里传给下层函数，深层函数所面对的不是越来越简单的问题，而是越来越复杂的问题，因为参数里带有前面若干步的运算路径。
	* [递归与尾递归总结](https://www.cnblogs.com/Anker/archive/2013/03/04/2943498.html) 

	
* **1到10000有多少个数字7（头条，说思路即可）**
	* [腾讯面试题-0到9999这1万个数中有多少个数字7](https://www.imooc.com/article/16642)（就是个思维题 Orz...） 


* 实现一个二叉搜索树的迭代器，包括 next() 和 hasNext() 方法（PayPal） *`TODO`* 


### 笔试真题快照

* **拼多多学霸批服务端 0728**
	* 1. 严格升序数组替换
		* 需要考虑替换哪一个数，逆序对需要全部提取出来，而不是仅仅考虑逆序对中小的那个，如：```1, 3, 8, 7, 10```， 替换8或者替换7都有可能(可以先考虑替换n+1，因为是选较大的数，不满足再替换n)
		* 同时还要考虑首尾情况，如：```10，5，6，7，8，9```，就只能替换10了
	* 2. 数组中单词首尾能否成环
		* 深度优先搜索（DFS） + 回溯法
		* 个人思路 (不适用于存在多个配对的情况)
			* judge(list, i, k, cur, flag[])
			* 首元素flag记为2，访问过记为1，最后一个元素与 flag==2 对应的字符串做判断
			* 剩下flag未遍历过的元素中找
	* 3. 任务优先级排序，任务间存在依赖关系，给出最优（累加时间最少）方案
		* 用小顶堆存储当前可执行的任务
		* 每次出堆后更新依赖
		* 把依赖为0的任务当做可执行任务入堆（维护一个依赖01数组）
	* 4. 堆积木，求积木的最高高度，要求下层积木体积必须大于上层，且某块积木上层的重量之和不能超过本身的7倍
		* 动态规划
		* dp[i][h]记录以第i块积木为底, 高为h的积木塔的最低重量
		* dp[i][h] = nodes[i].w + dp[j][h-1]（j 从 i-1 开始遍历）
	* [拼多多学霸批算法工程师笔试题经验](https://www.nowcoder.com/discuss/212363?type=2)

