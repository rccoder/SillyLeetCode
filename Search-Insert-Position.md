# Search Insert Position

Given a sorted array and a target value, return the index if the target is found. If not, return the index where it would be if it were inserted in order.

You may assume no duplicates in the array.

## 解题思路
- 最简单的做法是直接遍历，找到比它大的中断循环
- 如果数据比较多可以尝试二分

## JavaScript
``` javascript
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number}
 */
var searchInsert = function(nums, target) {
    let targetIndex = 0;
    for (let i = 0, l = nums.length; i < l; i++) {
        if (target > nums[i]) {
            targetIndex ++;
        }
    }
    return targetIndex;
};
```
