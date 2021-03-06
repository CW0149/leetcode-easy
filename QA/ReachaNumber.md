# [到达终点数字](https://leetcode-cn.com/problems/reach-a-number)

### 问题

在一根无限长的数轴上，你站在0的位置。终点在target的位置。

每次你可以选择向左或向右移动。第 n 次移动（从 1 开始），可以走 n 步。

返回到达终点需要的最小移动次数。

示例 1:

```
输入: target = 3
输出: 2
解释:
第一次移动，从 0 到 1 。
第二次移动，从 1 到 3 。
```
示例 2:

```
输入: target = 2
输出: 3
解释:
第一次移动，从 0 到 1 。
第二次移动，从 1 到 -1 。
第三次移动，从 -1 到 2 。
```
注意:

target是在[-10^9, 10^9]范围中的非零整数。

### 解答

```
/**
 * @param {number} target
 * @return {number}
 */
// 设想差一个n到达target
// 若x + n - target为偶数，则将前面(x+n-target)/2的数变成负数就行
// 若为奇数则需额外一两个
var reachNumber = function(target) {
    target = Math.abs(target)
    let n = (Math.sqrt(8 * target + 1) - 1) / 2
    if (Number.isInteger(n)) return n
    n = Math.ceil(n)
    return ((n + 1) * n / 2 - target) % 2 ? (n % 2 ? n + 2 : n + 1) : n
};
```
