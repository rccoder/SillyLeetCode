# Summary Ranges

Given a sorted integer array without duplicates, return the summary of its ranges.

For example, given [0,1,2,4,5,7], return ["0->2","4->5","7"].

## 解题思路

* 双指针
* 一样跳，不一样push，然后指针对齐

## JavaScript

``` javascript
/**
 * @param {number[]} nums
 * @return {string[]}
 */
var summaryRanges = function(nums) {
    var result = [];
    if(nums.length === 0) {
        return result;
    }
    var p = 0, q = 0;
    while(q < nums.length) {
        if(q < nums.length-1 && nums[q+1] === nums[q] + 1) {
            q++;
        } else {
            if(p === q) {
                result.push('' + nums[p]);
            } else {
                result.push(('' + nums[p] + '->' + nums[q]));
            }
            q ++;
            p = q;
        }
        
    }
    return result;
};
```
