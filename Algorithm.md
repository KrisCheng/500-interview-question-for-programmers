# Algorithm

本页面用于记录个人的刷题笔记（尤其是那些有启发，有趣的编程题）。部分附个人面试公司， 主要根据题型分类（跨题型随机分类2333）。

### 二叉树

* **非递归实现求二叉树的深度（小红书）** 
  * 引入队列，统计当前层次节点数目，逐层遍历
  * [二叉树的深度（递归和非递归）---java实现](https://blog.csdn.net/snow_7/article/details/51818580)
  * [102. 二叉树的层次遍历](https://leetcode-cn.com/problems/binary-tree-level-order-traversal/)


* **非递归从左至右打印一颗二叉树中的所有路径（拼多多/字节跳动）** 
  * [257. 二叉树的所有路径](https://leetcode-cn.com/problems/binary-tree-paths/) 
* **判断平衡二叉树（腾讯）** 

  * [110. 平衡二叉树](https://leetcode-cn.com/problems/balanced-binary-tree/) 


* **寻找二叉搜索树中第一个大于k的节点（微软）**
  * 中序遍历求值
  * 类似于 [230. 二叉搜索树中第K小的元素](https://leetcode-cn.com/problems/kth-smallest-element-in-a-bst/) 
* **二叉树的完全性检验（Unity）**

  * [958. 二叉树的完全性检验](https://leetcode-cn.com/problems/check-completeness-of-a-binary-tree/) 

* **根据前&中序遍历结果重建二叉树（Unity）**

  * 首先找到根节点，再划分左右子树区域，逐层递归找到左右子节点
  * [105. 从前序与中序遍历序列构造二叉树](https://leetcode-cn.com/problems/construct-binary-tree-from-preorder-and-inorder-traversal/) 
* **实现一个二叉搜索树迭代器，包括 `next() `和 `hasNext()` 方法（PayPal）**
  * [173. 二叉搜索树迭代器](https://leetcode-cn.com/problems/binary-search-tree-iterator/) 
* **二叉树的右视图（Shopee）**

  * [199. 二叉树的右视图](https://leetcode-cn.com/problems/binary-tree-right-side-view/)

* **给定一个二叉树根节点和指定路径，判断二叉树中是否存在给定指定路径，且要求指定路径最后一个元素为叶节点（微软）**
* **将一颗二叉搜索树转化成一个排序的双向链表**
  * 不能创建新结点
  * [二叉搜索树与双向链表](https://www.nowcoder.com/practice/947f6eb80d944a84850b0538bf0ec3a5?tpId=13&tqId=11179&rp=1&ru=/ta/coding-interviews&qru=/ta/coding-interviews/question-ranking) 


* **二叉树的最近公共祖先** 
  * 首先判断当前节点是否为指定结点，是则返回
  * 递归当前结点的左右子树
  * 如果两边均不为null，表示找到，返回当前结点，均为null则返回null，否则返回对应子节点（left / right）
  * [236. 二叉树的最近公共祖先](https://leetcode-cn.com/problems/lowest-common-ancestor-of-a-binary-tree/) 
  * [Lowest Common Ancestor Binary Tree](https://www.youtube.com/watch?v=13m9ZCB8gjw)（各种情况详细举例，推荐）


* **二叉树的中序遍历的下一个结点**
  * 先判断右子结点不为空，返回右子节点最左边的节点
  * 若父节点不为空，上溯到根节点的 “/”即返回
  * [二叉树的下一个结点](https://www.nowcoder.com/practice/9023a0c988684a53960365b889ceaf5e?tpId=13&tqId=11210&rp=3&ru=/ta/coding-interviews&qru=/ta/coding-interviews/question-ranking) 

* **红黑树描述及其复杂度分析（插入/查找）（腾讯/阿里）** 
  * 查找、插入、删除时间复杂度 --> O(logN)
  * [红黑树 Wiki](https://zh.wikipedia.org/wiki/%E7%BA%A2%E9%BB%91%E6%A0%91)
  * [26 | 红黑树（下）：掌握这些技巧，你也可以实现一个红黑树](https://time.geekbang.org/column/article/68976) （红黑树分析）


* **二叉树的直径** 
  * [543. 二叉树的直径](https://leetcode-cn.com/problems/diameter-of-binary-tree/) 
  
* **二叉树的遍历**
  * 引入一种新的数据结构形成通用解法（Value + 是否访问过的标识符）
  * 使用一个队列添加&删除节点
  * [二叉树的前序遍历](https://leetcode-cn.com/problems/binary-tree-preorder-traversal/) / [二叉树的中序遍历](https://leetcode-cn.com/problems/binary-tree-inorder-traversal/) / [二叉树的后序遍历](https://leetcode-cn.com/problems/binary-tree-postorder-traversal/) 



### 排序

* **把一个数组排成最大的数（阿里）**
  * [剑指 Offer 45. 把数组排成最小的数](https://leetcode-cn.com/problems/ba-shu-zu-pai-cheng-zui-xiao-de-shu-lcof/) 
  * 面试官说需要 通过 [补位](https://codeleading.com/article/55991386629/) 思想（普通的compare再sort并不满意，但补位思想似乎不适用于有重复元素的情况）
* **如何给一个很大的无序数组去重（腾讯）**
  * [26. 删除排序数组中的重复项](https://leetcode-cn.com/problems/remove-duplicates-from-sorted-array/)（给排序数组去重）
* **求两个排序数组的中位数（依图）**   
  * 要求时间复杂度 O(log(m+n)) 
  * 二分查找，递归求整个数组中第K大的元素，完整代码需要仔细考虑多种边界条件
  * [4.寻找两个有序数组的中位数](https://leetcode-cn.com/problems/median-of-two-sorted-arrays/) 
* **求一个循环递增数组的最小值（腾讯）** 
  * [153. 寻找旋转排序数组中的最小值](https://leetcode-cn.com/problems/find-minimum-in-rotated-sorted-array/description/) （无重复元素，二分，总有一半有序，注意边界）
  * [154. 寻找旋转排序数组中的最小值 II](https://leetcode-cn.com/problems/find-minimum-in-rotated-sorted-array-ii/) （有重复元素，需要解除相等时的死循环）
* **数组中的逆序对（星环）** 
  * 归并排序 && 递归的应用
  * 引入辅助数组临时存放排序好的数据
  * 归并时指向两个指针末尾，逐次向前并统计
  * [面试题51. 数组中的逆序对](https://leetcode-cn.com/problems/shu-zu-zhong-de-ni-xu-dui-lcof/) 


* **如何找到一个无序数组的中位数（Unity）**
  * [295. 数据流的中位数](https://leetcode-cn.com/problems/find-median-from-data-stream/) （建立两个堆，最大堆&最小堆，复杂度分析）
  * [找出一个无序数组的中位数](https://blog.csdn.net/oneday_789/article/details/76681764) （快排，缩小Partition区域 / 取一半元素建堆）


* **链表排序**
  * 需要 nlog(n) 时间复杂度和常数级空间复杂度
  * 归并排序的应用（Bottom Up）
  * 找到中点，断开链表（通过快慢两个指针）
  * 交替双指针合并
  * [148. 排序链表](https://leetcode-cn.com/problems/sort-list/)
* **手写主流排序算法 & 各种算法的复杂度/稳定性分析（腾讯/字节跳动/阿里/蜻蜓FM/Unity）**
  * 常见问题
    * 手写快排 / 堆排（Unity）
    * 快排的复杂度分析（最好/最坏/平均）
    * 堆排中建堆的时间复杂度分析  --> O(n)
      * [堆排序中建堆过程时间复杂度O(n)怎么来的？](https://www.zhihu.com/question/20729324) 
      * [为什么建堆的时间复杂度是O(n)？](https://blog.csdn.net/LeoSha/article/details/46116959)
    * 归并排序的 Top-Down & Bottom-up 策略
    * 不同排序的稳定性分析
    * 冒泡排序的优化策略（华为）
      * 设置flag位，一轮未交换数据即已完成排序，提前结束
      * 记住本轮最后一次交换发生的位置lastExchange，下次内层循环到此终止即可
  * [排序算法稳定性](https://baike.baidu.com/item/%E6%8E%92%E5%BA%8F%E7%AE%97%E6%B3%95%E7%A8%B3%E5%AE%9A%E6%80%A7)
  * [排序算法可视化](https://visualgo.net/en/sorting)
  * [快排 Wiki](https://zh.wikipedia.org/zh/%E5%BF%AB%E9%80%9F%E6%8E%92%E5%BA%8F) / [堆排 Wiki](https://zh.wikipedia.org/wiki/%E5%A0%86%E6%8E%92%E5%BA%8F) / [归并排序 Wiki](https://zh.wikipedia.org/wiki/%E5%BD%92%E5%B9%B6%E6%8E%92%E5%BA%8F)
  * [堆排序(Heapsort)](https://www.youtube.com/watch?v=j-DqQcNPGbE) （特别好的讲解）
  * [冒泡排序算法及其两种优化](https://blog.csdn.net/yanxiaolx/article/details/51622286)
* **（Top K 问题）给定一个无符号，包含10亿个数的数组，如何取出前100大的数（字节跳动/腾讯）**
  * 答题思路
    * 首先询问资源 --> 内存 / 核数 / 单机or多机，如可用多机 --> MapReduce思想
    * 堆排 O(nlogk)，可以单机处理海量数据（在内存受限情况下），如果k较小，趋近于 O(n)
      * 建立一个容量为k的大/小顶堆
      * n个元素逐一比较，O(logk) 完成删除和插入操作
    * 全局排序， O(nlogn) （数据量较小时才可行）
    * 冒泡（k个），O(kn)
    * 快排划分 O(n)， 每次递归处理一侧的数据，理论上可以理解为每次折半，缺点 --> 存在内存不够的问题，因为需要一次读入所有数据
  * [算法必学：经典的 Top K 问题](https://juejin.im/entry/5c565fb7f265da2d84105958)（基本思路篇）
  * [海量数据处理 - 10亿个数中找出最大的10000个数（top K问题）](https://blog.csdn.net/zyq522376829/article/details/47686867) （各种资源场景分析，面试前可参考）
  * [最小的K个数](https://www.nowcoder.com/practice/6a296eb82cf844ca8539b57c23e6e9bf?tpId=13&tqId=11182&rp=1&ru=/ta/coding-interviews&qru=/ta/coding-interviews/question-ranking)（代码实现，首选堆排）


* **Java自带的 sort() 方法是如何实现的（阿里）**
  * Array.sort() / Collections.sort()
  * DualPivotQuicksort（双轴快速排序）
  * [Arrays.sort和Collections.sort实现原理解析](https://blog.csdn.net/u011410529/article/details/56668545)
  * [Collections.sort()和Arrays.sort()排序算法选择](https://blog.csdn.net/TimHeath/article/details/68930482)
* **写一个快速划分数据集的算法，要求测试集用新数据，训练集用老数据（第四范式）**  
  * 数据格式为 Record（id, timestamp）
  * 函数签名为 division(ArrayList<Record> dataset, double ratio)， ratio为(0,1)的划分比例
  * 要求复杂度为O(n)
* **从一大段文本中找出TOP K 的高频词汇**
  * [System Design Interview - Top K Problem (Heavy Hitters)](https://www.youtube.com/watch?v=kx-XDoPjoHw) （系统设计角度思考本题，如何权衡性能和效率，较为高阶）
  * [347. 前K 个高频元素](https://leetcode-cn.com/problems/top-k-frequent-elements/) （数字频次代码实现，建堆，时间复杂度为nlog(k)）
  * [692. 前K个高频单词](https://leetcode-cn.com/problems/top-k-frequent-words/) （词汇频次代码实现，思路一致）




### 链表&堆&栈&队列

* **反转链表（小红书/腾讯/字节跳动）** 
  * [206. 反转链表](https://leetcode-cn.com/problems/reverse-linked-list/) 
* **环形链表（星环/微软）**
  * [141. 环形链表](https://leetcode-cn.com/problems/linked-list-cycle/)
  * [142. 环形链表 II](https://leetcode-cn.com/problems/linked-list-cycle-ii/)
* **判断一个序列是否为合理的出栈顺序（网易）** 
  * [946. 验证栈序列](https://leetcode-cn.com/problems/validate-stack-sequences/) 
* **最长有效括号（Wish）**
  * [32. 最长有效括号](https://leetcode-cn.com/problems/longest-valid-parentheses/) 
* **旋转链表（字节跳动）**

  * [61. 旋转链表](https://leetcode-cn.com/problems/rotate-list/) 
* **删除链表 M 个节点之后的 N 个节点（微软）**
  * 要求用递归，不能循环
  * [删除链表 M 个节点之后的 N 个节点](https://leetcode-cn.com/problems/delete-n-nodes-after-m-nodes-of-a-linked-list/)

* **复杂链表的复制**
  * 连接一个重复链表
  * 断链，拆分成两个链表
  * [138. 复制带随机指针的链表](https://leetcode-cn.com/problems/copy-list-with-random-pointer/) 


* **约瑟夫环问题** 
  * 推数学公式 / 蛮力法
  * [面试题62. 圆圈中最后剩下的数字](https://leetcode-cn.com/problems/yuan-quan-zhong-zui-hou-sheng-xia-de-shu-zi-lcof/) 
* **滑动窗口最大值**
  * 通过设计新的数据结构来降低复杂度，保存最大值&当前值，删除中间无关值
  * [239. 滑动窗口最大值](https://leetcode-cn.com/problems/sliding-window-maximum/) 



### 字符串

* **如何找出一个字符串中的最大不重复子串（蜻蜓FM/美团/Wish/字节跳动）**
  * 滑动窗口 --> 滑动窗口直到最后一个元素，每当碰到重复时（可用一个Map记录，表示字母和位置），左指针往后走至当前位置，每轮都进行比较，取最大长度。 / 时间复杂度 --> O(n)
  * [3. 无重复字符的最长子串](https://leetcode-cn.com/problems/longest-substring-without-repeating-characters/)
* **给定一个数，删除K位得到最大值（Unity）**
  * 单调栈
  * [402. 移掉K位数字](https://leetcode-cn.com/problems/remove-k-digits/) 
* **至多包含 K 个不同字符的最长子串**
  * [340. 至多包含 K 个不同字符的最长子串](https://leetcode-cn.com/problems/longest-substring-with-at-most-k-distinct-characters/)

* **字符串的排列**
  * 深度优先搜索（DFS） + 剪枝
  * 理解递归的构造过程 --> 每次固定一个字符，继续处理剩余字符
  * 处理后还原交换（保证所有可能都被遍历到）
  * [面试题38. 字符串的排列](https://leetcode-cn.com/problems/zi-fu-chuan-de-pai-lie-lcof/)
  * [46. 全排列](https://leetcode-cn.com/problems/permutations/) （相同思路）


* **至少有K个重复字符的最长子串**

  * 分治法，递归求解
  * 用一个map计数，一个set存储不应该包含的字母（即 count < k）
  * 双指针遍历字符串，一旦找到需要剔除的字符，判断该字符左右两边满足条件的最长子串，比较返回较大值
  * [395. 至少有K个重复字符的最长子串](https://leetcode-cn.com/problems/longest-substring-with-at-least-k-repeating-characters/) 




### 递归&回溯


* **分割回文串**
  * [131. 分割回文串](https://leetcode-cn.com/problems/palindrome-partitioning/) 
* **八皇后问题**
  * [面试题 08.12. 八皇后](https://leetcode-cn.com/problems/eight-queens-lcci/)
* **24点问题及其优化（叽里呱啦）**
  * 大意和 [679. 24 点游戏](https://leetcode-cn.com/problems/24-game/) 类似



### 图

* **岛屿数量（爱奇艺/依图）**

  * [200. 岛屿数量](https://leetcode-cn.com/problems/number-of-islands/) 

* **连通网络的操作次数（eBay）**
  * [1319. 连通网络的操作次数](https://leetcode-cn.com/problems/number-of-operations-to-make-network-connected/) 

* **给定一个二维整形矩阵[m] [n]，输出一个重新排列后的矩阵，满足：**

  [x] <= [x] >= [x] <= [x] ...

  [x]  >= [x] <= [x] >= [x] ...

  [x] <= [x] >= [x] <= [x] ...
  **列元素也是相同逻辑，交替大于小于（输出一个候选解即可）  （NewsBreak）**

* **解数独（微软）**

  * [解数独](https://leetcode-cn.com/problems/sudoku-solver/)

* **一个无向图，实现 isConnected(Node A, Node B) 和 connect(Node A, Node B) 方法（Morgan Stanley）**

  * 类似 [面试题 04.01. 节点间通路](https://leetcode-cn.com/problems/route-between-nodes-lcci/)，但不完全一样（有向、无向）

* **课程表问题**

  * [207. 课程表](https://leetcode-cn.com/problems/course-schedule/) 
  * [210. 课程表 II](https://leetcode-cn.com/problems/course-schedule-ii/)
  * [630. 课程表 III](https://leetcode-cn.com/problems/course-schedule-iii/) 



### 动态规划


* **最佳折扣问题（EA）**

  * double calculateMinPrice(int [] counts, double [] prices, Map<int[], Double> promotions)
  * counts表示一个要买的商品数量列表（如0011表示第3件和第4件都买一个），prices表示单价，promotions表示折扣表 比如 0011->9 表示第3件和第4件一起打包买打9折，输出一个最低价格
  * 实现类似 [动态规划_最小费用购物问题](https://blog.csdn.net/OddSmurfs/article/details/94107909)
* **设计一个模糊匹配算法，给定一个字符串列表和一个字符串，输出列表中最匹配的那个（若都不匹配可输出空串）（微软）**

  * 类似于 [72. 编辑距离](https://leetcode-cn.com/problems/edit-distance/)，基于字符长度配置好阈值（个人实现，不知道是否为意向答案，反正过了）
* **最长回文子串（百度/字节跳动）**
  * [5. 最长回文子串](https://leetcode-cn.com/problems/longest-palindromic-substring/) 
* **完全平方数（微软）**

  * [279. 完全平方数](https://leetcode-cn.com/problems/perfect-squares/)
* **最长递增子序列（微软）**

  * [300. 最长递增子序列](https://leetcode-cn.com/problems/longest-increasing-subsequence/)

* **正则表达式匹配**
  * [10. 正则表达式匹配](https://leetcode-cn.com/problems/regular-expression-matching/) 
* **零钱兑换** 
  * [322. 零钱兑换](https://leetcode-cn.com/problems/coin-change/)
* **鸡蛋掉落**
  * dp[K] [N] = 1 + max(dp[K - 1] [i - 1] + dp[K] [N - i]) + 1  (i~(1,N)) （K蛋N层，最直观的DP，还有其他解法）
  * [887. 鸡蛋掉落](https://leetcode-cn.com/problems/super-egg-drop/) 
  * [Egg Dropping Dynamic Programming](https://www.youtube.com/watch?v=3hcaVyX00_4) （画状态转移表）


* **单词拆分**  

  * [139. 单词拆分](https://leetcode-cn.com/problems/word-break/) 
  * [140. 单词拆分 II](https://leetcode-cn.com/problems/word-break-ii/) 
* **完全平方数**

  * [279. 完全平方数](https://leetcode-cn.com/problems/perfect-squares/) 



### 设计模式

* **实现一个线程安全的单例模式（星环/阿里）**
  * 懒汉模式 --> Lazy初始化
  * 饿汉模式 --> 在方法调用前，实例就已经创建好了
  * 全部 sychronized 锁住 --> 可以保证线程安全，但销效率低
  * “双重检查锁” 机制版本 （面试用，注意 `getInstance()` 方法 和对应 instance 实例 都需要 `static` 关键字修饰）
    * volatile 来保证其线程间的可见性，禁止指令重排序，保证返回的是初始化**完全**的对象，详见 [Why is volatile used in double checked locking](https://stackoverflow.com/questions/7855700/why-is-volatile-used-in-double-checked-locking) 
    * 同步代码块中使用二次检查，以保证其不被重复实例化
  * 枚举enum和静态代码块的特性相似，在使用枚举时，构造方法会被自动调用，利用这一特性也可以实现单例（面试也可稍微提及）
  * [高并发下线程安全的单例模式（最全最经典）](https://blog.csdn.net/cselmu9/article/details/51366946) （单例的N种实现）
  * [单例模式](https://www.runoob.com/design-pattern/singleton-pattern.html)（详尽介绍）
  
* **设计一个方案，提供不同算法调用接口（参数即为需要调用的方法名）（PayPal）**
  * 这题感觉非常开放，当时答了用 适配器模式，似乎面试官并不是特别满意，适配器模式 属于结构型模式，主要用于解决兼容性问题，实际此题还是以如何创建为主，用 [工厂模式](https://www.runoob.com/design-pattern/factory-pattern.html) 为宜


* **设计一个方案，传入一个类型（如 圆形，矩形，三角形等），求对应的周长和面积，能用设计模式更好（字节跳动）** 

  * 不使用设计模式的版本见 [Java小程序之计算三角形/圆形/矩形的周长和面积](https://blog.csdn.net/Class_Lkr/article/details/51211269) 
  * [策略模式](https://www.runoob.com/design-pattern/strategy-pattern.html) ，将获取周长和面积的方法公共提取，将对应对象（圆/矩形等）作为参数传入，采用不同运算，详见 [get-designpatterns](https://github.com/get-set/get-designpatterns) 
* **（项目相关）个人项目的查询引擎设置 AbstractProvider 这种抽象类用到了什么模式（星环）**
  * 模板模式（Template Pattern）
  * 提取通用方法，便于维护 / 封装不变部分，扩展可变部分




### 数据库设计&SQL

* **设计一个表结构，用于记录高考之后学生的成绩，以及写一个查询得到某个城市的理科前十名（字节跳动）** 
  * 具体题意忘了，`limit` 即可筛出前n条，但原意应该不止如此

* **设计一个消息分发系统的表结构，需要满足 1.对某个用户发消息 2.对某类用户发消息 3.对所有用户发消息 （字节跳动）**
* **找出在表A中但不在表B中的记录（根据某一个共同的column）（PayPal）**
  * [查询A、B表中，A表中B表没有的数据](https://blog.csdn.net/long636/article/details/51733273)（三种方法）




### 其他

* **LRU Cache（腾讯/Shopee/PayPal/Morgan Stanley）**
  * 头尾两个伪节点（避免判断） + 双向链表
  * [146. LRU 缓存](https://leetcode-cn.com/problems/lru-cache/)
* **买卖股票的最佳时机系列（野村证券/字节跳动/携程）** 
  * [121. 买卖股票的最佳时机](https://leetcode-cn.com/problems/best-time-to-buy-and-sell-stock/) 
* **实现一个HashMap（微软）**
  * 要求：1. 定义内部存储结构； 2.实现 insert(key, value) 和 remove(key)；3.不能使用任何Java集合框架。
  * [706. 设计哈希映射](https://leetcode-cn.com/problems/design-hashmap/)
  * [自己动手实现一个HashMap](https://winnerchen.github.io/yiheng.github.io/2017/08/26/%E8%87%AA%E5%B7%B1%E5%8A%A8%E6%89%8B%E5%AE%9E%E7%8E%B0%E4%B8%80%E4%B8%AAHashMap/) （将Entry设置为单链表节点，删除时参考 [剑指 Offer 18. 删除链表的节点 ](https://leetcode-cn.com/problems/shan-chu-lian-biao-de-jie-dian-lcof/)）

* **求给定区间内子区间的最大值（区间内最小值*区间元素相加）（字节跳动）**
  * 要求时间复杂度O(n)
  * [原题](https://www.nowcoder.com/questionTerminal/e6e57ef2771541dfa2f1720e50bebc9a) 

* **斐波那契数列的尾递归实现（Wish）**
  * 面试官原意是斐波那契的递归实现如何优化
  * 尾递归就是把当前的运算结果（或路径）放在参数里传给下层函数
  * [递归与尾递归总结](https://www.cnblogs.com/Anker/archive/2013/03/04/2943498.html) 
* **1到10000有多少个数字7（字节跳动，说思路即可）**
  * 答案 ：4000
  * [腾讯面试题-0到9999这1万个数中有多少个数字7](https://www.imooc.com/article/16642) 
* **给定精度（如小数点后10位），写一个函数求根号2的具体值（拼多多/字节跳动）** 
  * 牛顿法，详见 [如何通俗易懂地讲解牛顿迭代法求开方？数值分析？](https://www.zhihu.com/question/20690553)
  * [69. x 的平方根](https://leetcode-cn.com/problems/sqrtx/) 


* **给定一个乱序数组[0,100]，替换其中一个数，找出这个被替换的数（字节跳动）** 
  * 类似 [142. 环形链表 II](https://leetcode-cn.com/problems/linked-list-cycle-ii/) 思路，重复数字会形成环，双指针寻找（略奇技淫巧）
  * [287. 寻找重复数](https://leetcode-cn.com/problems/find-the-duplicate-number/) 
* **缺失的第一个正数（字节跳动）**

  * [41. 缺失的第一个正数](https://leetcode-cn.com/problems/first-missing-positive/)


* **顺时针打印矩阵（星环）** 
  * [54. 螺旋矩阵](https://leetcode-cn.com/problems/spiral-matrix/) 
* **实现一个int转中文表示的函数，同时设计测试用例（微软）**
  * 定界数据范围 + 梳理演变规则（以“万”为节，化繁为简，以及“零”如何处理）
  * [数字(int型范围内正整数)和中文的相互转换](https://blog.csdn.net/pjz161026/article/details/55049307) 
* **100盏灯问题（百度）**

  * [面试题—100盏灯问题](https://blog.csdn.net/qq_39539470/article/details/79978917) 
* **给定一个数组，一个闭区间[n,m]，给出该数组中所有最大值在闭区间中的连续子数组数目（Shopee）**

  * 要求时间复杂度O(n)
  * 如 [2,1,4,3]，[2,3]，有[2],[2,1],[3]，返回3
* **字符串相乘（微软）**

  * [43. 字符串相乘](https://leetcode-cn.com/problems/multiply-strings/)

* **用Java实现一个String转Map（Map<String,Object>）的函数，不能使用String的split和第三方库（喜马拉雅）**


* **整数中1出现的次数（从1到n中1出现的次数）**
  * [233. 数字 1 的个数](https://leetcode-cn.com/problems/number-of-digit-one/) 


* **单词接龙**
  * 广度优先 --> 队列 + 暴力搜索（遍历过的单词删除），视频讲解见 [花花酱 LeetCode 127. Word Ladder - 刷题找工作 EP71](https://www.youtube.com/watch?v=vWPCm69MSfs) 
  * [127. 单词接龙](https://leetcode-cn.com/problems/word-ladder/) 


* **分数到小数** 
  * 将除法过程代码化
  * [166. 分数到小数](https://leetcode-cn.com/problems/fraction-to-recurring-decimal/) 
* **只出现一次的数字** 
  * [136. 只出现一次的数字](https://leetcode-cn.com/problems/single-number/) 
* **分糖果**
  * 从左至右扫一遍，再从右至左扫一遍，取两遍中的最大值
  * [135. 分发糖果](https://leetcode-cn.com/problems/candy/) 
* **实现一个命令行逆波兰计算器**

  * [CommandLineRPN](https://github.com/KrisCheng/CommandLineRPN) 
* **Largest M-aligned Subset**
  * [Microsoft | OA 2020 | Largest M-aligned Subset](https://leetcode.com/discuss/interview-question/525894/)