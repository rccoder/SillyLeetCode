# Move-Zeroes

Given an array nums, write a function to move all 0's to the end of it while maintaining the relative order of the non-zero elements.

For example, given nums = [0, 1, 0, 3, 12], after calling your function, nums should be [1, 3, 12, 0, 0].

**Note:**

You must do this in-place without making a copy of the array.

Minimize the total number of operations.

## 解题思路

* 双指针
* 一个持续扫描
* 一个后面，前面遇到不是0的就置换到前面

## JavaScript

``` javascript
/**
 * @param {number[]} nums
 * @return {void} Do not return anything, modify nums in-place instead.
 */
var moveZeroes = function(nums) {
    var p = 0, q = 0;
    var numsLength = nums.length;
    for(var i = 0; i < numsLength; i++) {
        var tep;
        if(nums[i] !== 0) {
            tep = nums[i];
            nums[i] = nums[p];
            nums[p] = tep;
            p++;
        }
    }
};
```
