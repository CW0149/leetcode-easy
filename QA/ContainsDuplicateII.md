# [存在重复元素 II](https://leetcode-cn.com/problems/contains-duplicate-ii)

### 问题


给定一个整数数组和一个整数 k，判断数组中是否存在两个不同的索引 i 和 j，使得 nums [i] = nums [j]，并且 i 和 j 的差的绝对值最大为 k。

示例 1:

```
输入: nums = [1,2,3,1], k = 3
输出: true
```
示例 2:

```
输入: nums = [1,0,1,1], k = 1
输出: true
```
示例 3:

```
输入: nums = [1,2,3,1,2,3], k = 2
输出: false
```

### 解答

```
/**
 * @param {number[]} nums
 * @param {number} k
 * @return {boolean}
 */
// 注意0与undefined
var containsNearbyDuplicate = function(nums, k) {
    var map = {};
    for (var i = 0; i < nums.length; i += 1) {
        var num = nums[i];
        if ((map[num] + 1) && (i - map[num] <= k)) return true;
        map[num] = i;
    }
    return false;
};
```