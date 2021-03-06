# [最长回文串](https://leetcode-cn.com/problems/longest-palindrome)

### 问题

给定一个包含大写字母和小写字母的字符串，找到通过这些字母构造成的最长的回文串。

在构造过程中，请注意区分大小写。比如 "Aa" 不能当做一个回文字符串。

注意:
假设字符串的长度不会超过 1010。

示例 1:

```
输入:
"abccccdd"

输出:
7
```

解释:
我们可以构造的最长的回文串是"dccaccd", 它的长度是 7。

### 解答

```
/**
 * @param {string} s
 * @return {number}
 */
var longestPalindrome = function(s) {
    var len = 0, mp = {};
    for (var i = 0; i < s.length; i += 1) {
        mp[s[i]] ^= s[i].charCodeAt();
        if (mp[s[i]] === 0) {
            len += 2;
            delete mp[s[i]];
        }
    }
    return Object.keys(mp).length ? len + 1 : len;
};
```