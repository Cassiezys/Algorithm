## 1.背包，目标和问题

> 所有元素任意加减得到目标值
>
> `dp[i][j]`: 前`i`个元素加减后得到`j`的方案数为`dp[i][j]`
>
> 对于nums中的每一个num， 遍历0<=j<=target：
>
> - 如果`j<num`, 则无法选num，则`dp[i][j]` = `dp[i-1][j]`
> - 如果`j>=num`, 则可以不选或选num，则`dp[i][j]`=`dp[i-1][j]+dp[i-1][j-num]`

```python
dp = [[0 for _ in range(target+1)]for_ in range(len(nums)+1)]
dp[0][0]=1
for i in range(1,len(nums)+1):
  num = nums[i]
  	for j in range(target+1):
      dp[i][j] = dp[i-1][j]
      if j>=num:
        dp[i][j] += dp[i-1][j-num]
return dp[len(nums)][target]
```

根据第二行都只与第一行有关

```python
dp = [0]*(neg+1)
dp[0]=1
for num in nums:
  for j in range(target,num-1, -1):
    dp[j] += dp[j-num]
return dp[target]
```

https://leetcode-cn.com/problems/target-sum/

## 组合

> 1.自顶向下：dp(rem) = dp(rem-coin)+1
>
> 2.自底向上：dp[j] = min(dp[j], dp[j-coin]+1)
>
> 3.BFS(最少硬币数量)

### 数字之和

> `dp[i][j]`定义为在数组nums中的前`i`个数中选取元素，使之和为`j`的方案数。
>
> 目标和为neg，则求的目标为`dp[n][neg]`：
>
> ![image-20220410163856190](/Users/niannian/Library/Application Support/typora-user-images/image-20220410163856190.png)

```python
dp = [[0]*(neg+1) for _ in range(n+1)]
dp[0][0] = 1
for i in range(1,n+1):
  num = nums[i-1]
  for j in range(neg+1):
  	dp[i][j] = dp[i-1][j]
    if j>=num:
      dp[i][j] += dp[i-1][j-num]
return dp[n][neg]
```

由于`dp[i][x]`的值只与`dp[i-1][x]`行的值有关，利用滚动数组

```python
dp = [0]*(neg+1)
dp[0] = 1
for num in nums:
  for j in range(neg, num-1, -1):
    dp[j] += dp[j-num]
return dp[neg]
```



