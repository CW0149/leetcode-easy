# [七进制数](https://leetcode-cn.com/problems/base-7)

### 问题

给定一个整数，将其转化为7进制，并以字符串形式输出。

示例 1:

```
输入: 100
输出: "202"
```
示例 2:

```
输入: -7
输出: "-10"
```
注意: 输入范围是 [-1e7, 1e7] 。

### 解答

```
/**
 * @param {number} num
 * @return {string}
 */
var convertToBase7 = function(num) {
    var s = '', sign = num < 0 ? '-' : '', num = Math.abs(num);
    while (num) {
        s = num % 7 + s;
        num = ~~(num / 7);
    }
    return sign + s || '0';
};
```