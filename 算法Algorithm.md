### 八大算法思想：

- 双指针

  - [167-两数之和](https://leetcode-cn.com/problems/two-sum-ii-input-array-is-sorted/)

    > 有序： 二分查找

  - [633.平方数之和](https://leetcode-cn.com/problems/sum-of-square-numbers/description/)

  - [345. 反转字符串中的元音字母](https://leetcode-cn.com/problems/reverse-vowels-of-a-string/)

  - [680. 验证回文字符串 Ⅱ](https://leetcode-cn.com/problems/valid-palindrome-ii/)

  - [88. 合并两个有序数组](https://leetcode-cn.com/problems/merge-sorted-array/)

  - [141. 环形链表](https://leetcode-cn.com/problems/linked-list-cycle/)

  - [142. 环形链表 II](https://leetcode-cn.com/problems/linked-list-cycle-ii/)

  - [524. 通过删除字母匹配到字典里最长单词](https://leetcode-cn.com/problems/longest-word-in-dictionary-through-deleting/)

    > 字典序排序：`lists.sort(key=lambda x:(-len(x),x))`字符串长度降序，字典序升序

- 排序

  - 求解 **K-Element**，**TopK Elements** 问题
    - 快排：
      - [215. 数组中的第K个最大元素](https://leetcode-cn.com/problems/kth-largest-element-in-an-array/)
      - 自定义排序成最小数组

    - 堆排
      - 维护数组的前k小
      - 无序序列的中位数

    - 桶排
      - [347. 前 K 个高频元素](https://leetcode-cn.com/problems/top-k-frequent-elements/)
      - [451. 根据字符出现频率排序](https://leetcode-cn.com/problems/sort-characters-by-frequency/)

  - 指定排序：
    - [75. 颜色分类](https://leetcode-cn.com/problems/sort-colors/)

- 贪心思想：

  > 操作为局部最优，最后得到全局最优的结果

  - [455. 分发饼干](https://leetcode-cn.com/problems/assign-cookies/)

  - [ ] [435. 无重叠区间](https://leetcode-cn.com/problems/non-overlapping-intervals/)

  - [ ] [452. 用最少数量的箭引爆气球](https://leetcode-cn.com/problems/minimum-number-of-arrows-to-burst-balloons/)

  - [ ] [406. 根据身高重建队列](https://leetcode-cn.com/problems/queue-reconstruction-by-height/)

  - [121. 买卖股票的最佳时机](https://leetcode-cn.com/problems/best-time-to-buy-and-sell-stock/)
  - [122. 买卖股票的最佳时机 II](https://leetcode-cn.com/problems/best-time-to-buy-and-sell-stock-ii/)
  - [ ] [123. 买卖股票的最佳时机 III](https://leetcode-cn.com/problems/best-time-to-buy-and-sell-stock-iii/)
  - [605. 种花问题](https://leetcode-cn.com/problems/can-place-flowers/)
  - `DP`[392. 判断子序列](https://leetcode-cn.com/problems/is-subsequence/)
  - [665. 非递减数列](https://leetcode-cn.com/problems/non-decreasing-array/)
  - [53. 最大子数组和](https://leetcode-cn.com/problems/maximum-subarray/)
  - [ ] [763. 划分字母区间](https://leetcode-cn.com/problems/partition-labels/)

- 二分搜索

  - 有序列表  搜索准确值

    - [69. x 的平方根 ](https://leetcode-cn.com/problems/sqrtx/)

  - 有序列表  寻找边界，查找区间

    - [ ] [744. 寻找比目标字母大的最小字母](https://leetcode-cn.com/problems/find-smallest-letter-greater-than-target/)

    - [ ] [540. 有序数组中的单一元素](https://leetcode-cn.com/problems/single-element-in-a-sorted-array/)

    - [278. 第一个错误的版本](https://leetcode-cn.com/problems/first-bad-version/)

    - [ ] [153. 寻找旋转排序数组中的最小值](https://leetcode-cn.com/problems/find-minimum-in-rotated-sorted-array/)

    - [34. 在排序数组中查找元素的第一个和最后一个位置](https://leetcode-cn.com/problems/find-first-and-last-position-of-element-in-sorted-array/)--[剑指 Offer 53 - I. 在排序数组中查找数字 I](https://leetcode-cn.com/problems/zai-pai-xu-shu-zu-zhong-cha-zhao-shu-zi-lcof/)

- 分治

  > 分治法三步走：1.分解: 2.解决：3.合并

  - [ ] [241. 为运算表达式设计优先级](https://leetcode-cn.com/problems/different-ways-to-add-parentheses/)

    > x op y 结果取决于 x op y 1.分解：将运算符分成左右两部分，分别求解 2.实现递归，输入算式，返回算式解 3.根据运算符左右两部分得出最终解

  - [ ] [95. 不同的二叉搜索树 II](https://leetcode-cn.com/problems/unique-binary-search-trees-ii/)
  - 二叉树找公共结点

- 搜索（DFS、BFS）

  - BFS

    > 每一层遍历的节点都与根节点距离相同, 可以求解最短路径等 **最优解** 问题:
    >
    > - 队列：用来存储每一轮遍历得到的节点；
    > - 标记：对于遍历过的节点，应该将它标记，防止重复遍历

    - [1091. 二进制矩阵中的最短路径](https://leetcode-cn.com/problems/shortest-path-in-binary-matrix/)

    - [ ] `dp`[279. 完全平方数](https://leetcode-cn.com/problems/perfect-squares/)

      > 自顶向下： `dp[rem] = min{1<=i<=r}(dp[rem-i*i])+1`
      >
      > 自底向上：`dp[j] = min{1<=i<=r,i*i<=j<=n}min(dp[j], dp[j-i*i]+1)`
      >
      > 四平方定理：任意一个正整数n最多被表示为4个正整数的平方和：满足`n==4^k*(8*m+7)`，n为4个正整数，不等于为1，2，3个。

    - [127. 单词接龙](https://leetcode-cn.com/problems/word-ladder/)

  - DFS

    > 得到一个新节点时立即对新节点进行遍历, 执行到特定位置返回即可，求解能够遍历到节点 **可达性** 问题
    >
    > - 栈：用栈来保存当前节点信息，当遍历新节点返回时能够继续遍历当前节点。可以使用递归栈。
    > - 标记：和 BFS 一样同样需要对已经遍历过的节点进行标记。

    - [695. 岛屿的最大面积](https://leetcode-cn.com/problems/max-area-of-island/)
    - [200. 岛屿数量](https://leetcode-cn.com/problems/number-of-islands/)
    - [547. 省份数量](https://leetcode-cn.com/problems/number-of-provinces/)
    - [130. 被围绕的区域](https://leetcode-cn.com/problems/surrounded-regions/)

    - [ ] [417. 太平洋大西洋水流问题](https://leetcode-cn.com/problems/pacific-atlantic-water-flow/)

  - BackTracking（回溯）

    > 执行到指定位置返回之后仍需继续执行求解过程，求解 **排列组合** 问题：
    >
    > - 在访问一个新元素进入新的递归调用时，需要将新元素标记为已经访问，这样才能在继续递归调用时不用重复访问该元素；
    > - 但是在递归返回时，需要将元素标记为未访问，因为只需要保证在一个递归链中不同时访问一个元素，可以访问已经访问过但是不在当前递归链中的元素。

    - [17. 电话号码的字母组合](https://leetcode-cn.com/problems/letter-combinations-of-a-phone-number/)

    - [ ] [93. 复原 IP 地址](https://leetcode-cn.com/problems/restore-ip-addresses/)

    - [79. 单词搜索](https://leetcode-cn.com/problems/word-search/)
    - [257. 二叉树的所有路径](https://leetcode-cn.com/problems/binary-tree-paths/)
    - [46. 全排列](https://leetcode-cn.com/problems/permutations/)
    - [47. 全排列 II](https://leetcode-cn.com/problems/permutations-ii/)
    - [77. 组合](https://leetcode-cn.com/problems/combinations/)
    - [39. 组合总和](https://leetcode-cn.com/problems/combination-sum/)

    - [ ] [40. 组合总和 II](https://leetcode-cn.com/problems/combination-sum-ii/)

      > 删除列表中的多个元素，注意浅拷贝和深拷贝：添加元素、不添加元素

    - [216. 组合总和 III](https://leetcode-cn.com/problems/combination-sum-iii/)

    - [ ] [78. 子集](https://leetcode-cn.com/problems/subsets/)

      > 和40相像，添加元素｜不添加元素

    - [131. 分割回文串](https://leetcode-cn.com/problems/palindrome-partitioning/)

      > 出现多个条件的时候，先存储条件情况

    - [37. 解数独](https://leetcode-cn.com/problems/sudoku-solver/)

      > Dfs 优化到 位运算，枚举

    - [ ] [51. N 皇后](https://leetcode-cn.com/problems/n-queens/)

- 动态规划

  - 斐波那契数列：
    - [70. 爬楼梯](https://leetcode-cn.com/problems/climbing-stairs/)
    - [198. 打家劫舍](https://leetcode-cn.com/problems/house-robber/)
    - [213. 打家劫舍 II](https://leetcode-cn.com/problems/house-robber-ii/)

  - 矩阵路径
    - [64. 最小路径和](https://leetcode-cn.com/problems/minimum-path-sum/)
    - [62. 不同路径](https://leetcode-cn.com/problems/unique-paths/)

  - 数组区间

    - [303. 区域和检索 - 数组不可变](https://leetcode-cn.com/problems/range-sum-query-immutable/)
    - [ ] [413. 等差数列划分](https://leetcode-cn.com/problems/arithmetic-slices/)

  - 分割整数

    - [ ] [343. 整数拆分](https://leetcode-cn.com/problems/integer-break/)

      > 数字n尽可能以因子3等分时，乘积最大(快速幂)

    - [279. 完全平方数](https://leetcode-cn.com/problems/perfect-squares/) BFS中也有出现

    - [ ] [91. 解码方法](https://leetcode-cn.com/problems/decode-ways/) 和编码不同

  - 最长递增子序列

    > **子序列** 是由数组派生而来的序列，删除（或不删除）数组中的元素而不改变其余元素的顺序。
    >
    > `dp[n]`表示以S<sub>n</sub>为**结尾**的序列最长递增子序列长度：dp[n] = max(1,dp[i]+1)(1<=i<n) 

    - [ ] [300. 最长递增子序列](https://leetcode-cn.com/problems/longest-increasing-subsequence/)

      > 无序列表中单调性（维护递增子序列d）：二分查找，数组d的长度为最长子序列**长度**

    - [646. 最长数对链](https://leetcode-cn.com/problems/maximum-length-of-pair-chain/) 同上利用二分？？

    - [ ] [376. 摆动序列](https://leetcode-cn.com/problems/wiggle-subsequence/)

    > 利用状态设置两个状态数组；优化动态规划
    >
    > 贪心，记录每次‘峰’‘谷’。

  - 最长公共子序列

    > `dp[i][j]`存储S<sub>1</sub> 的前i-1个和S<sub>2</sub>的前j个字符 或S<sub>1</sub> 的前i个和S<sub>2</sub>的前j-1个字符 最长公共子序列
    >
    > `dp[i][j] = dp[i-1][j-1]+1` (S[i]==T[j])
    >
    > `dp[i][j] = max(dp[i-1][j], dp[i][j-1] )` (S[i]!=T[j])

    - [1143. 最长公共子序列](https://leetcode-cn.com/problems/longest-common-subsequence/)

  - 0 - 1 背包

    > 容量为W的背包，N件物品，求装物品的价值最大。物品属性：体积w和价值v
    >
    > `dp[i][j]`代表前i件物品体积不超过j的情况下达到的最大价值：
    >
    > `dp[i][j] = max(dp[i-1][j], dp[i-1][j-w]+v)`,(不装第i件物品，装第i件物品)

    ```python
    def bagpack(W,N, weights, values): 
      dp = [[0]*(W+1) for _ in range(N+1)]
      for i in range(1,N+1):
        w,v = weights[i-1], values[i-1]
        for j in range(1,W+1):
          dp[i][j] = dp[i-1][j]
          if j>=w:
            dp[i][j] =max(dp[i][j], dp[i-1][j-w]+v)
      return dp[N][W]
    ======================转为一维=============== dp[j] = max(dp[j], dp[j-w]+v) 
    	dp = [0]*(W+1)
      for i in range(1,N+1):
        w,v = weights[i-1], values[i-1]
        for j in range(W, w-1, -1):
          dp[j] = max(dp[j], dp[j-w]+v)
      return dp[W]
    =======================完全背包：将逆序遍历dp数组改为正序遍历：
    	for coin in coins:
        for j in range(coin, amount+1):
          dp[j] = max(dp[j], dp[j-coin]+1)
      
    ```

    > - 完全背包：物品为无限个； 
    >
    > - 多重背包：数量有限制； 
    >
    > - 多维费用背包：重量体积多重限制；
    >
    > - 其他：物品之间有关系；

    - [ ] [416. 分割等和子集](https://leetcode-cn.com/problems/partition-equal-subset-sum/)

      > `dp[i][j]`定义为在nums前i中选取若干正整数，是否存在和为j的方案

    - [ ] [494. 目标和](https://leetcode-cn.com/problems/target-sum/)

      > `dp[i][j]`定义为在nums前i中选取数字，和为j的方案数
      >
      > DFS 解法

    - [ ] [474. 一和零](https://leetcode-cn.com/problems/ones-and-zeroes/)

    - [ ] [322. 零钱兑换](https://leetcode-cn.com/problems/coin-change/)

      > 最少硬币的数量，`dp[i]`表示金额i所需要的最少硬币数量

    - [ ] [518. 零钱兑换 II](https://leetcode-cn.com/problems/coin-change-2/)

      > 硬币的组合数` dp[i]`表示金额之和为i的硬币组合数字

    - [ ] [139. 单词拆分](https://leetcode-cn.com/problems/word-break/)

      > `dp[i]`表示字符串s前i个字符组成的字符串s[0...i-1]能否被空格拆分成字典中出现的单词

- 

- 数学

### 八大数据结构：

- 数组
- 链表
- 数
- 队列和栈
- 字符串
- 哈希表
- 图
- 位运算