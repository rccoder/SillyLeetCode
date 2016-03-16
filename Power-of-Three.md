# Power of Three

Given an integer, write a function to determine if it is a power of three.

```
Follow up:
Could you do it without using any loop / recursion?
```

## 解题思路

* 递归
* 其他待定

## JavaScript

``` javascript
/**
 * @param {number} n
 * @return {boolean}
 */
var isPowerOfThree = function(n) {
    if(n === 1) return true;
    else if(n === 0 || n % 3 !== 0) return false;
    return isPowerOfThree(n/3);
};
```
