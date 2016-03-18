# Remove Duplicates from Sorted Array

Given a sorted array, remove the duplicates in place such that each element appear only once and return the new length.

Do not allocate extra space for another array, you must do this in place with constant memory.

For example,

Given input array nums = [1,1,2],

Your function should return length = 2, with the first two elements of nums being 1 and 2 respectively. It doesn't matter what you leave beyond the new length.

## 解题思路

* 双指针
* 往前覆盖

## JavaScript

``` javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
var removeDuplicates = function(nums) {
    var p = 0, q = 1;
    var numsLength = nums.length;
    if(numsLength < 2) {
        return nums;
    }
    while(p < numsLength && q < nums.length) {
        if(nums[p] === nums[q]) {
            q++;
        } else {
            nums[++p] = nums[q++];
        }
    }
    
    nums.splice(p, numsLength-p-1);
    return nums.length;
    
};
```
