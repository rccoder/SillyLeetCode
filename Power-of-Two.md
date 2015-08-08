Power of Two
===
Given an integer, write a function to determine if it is a power of two.

## 解题思路

2的幂

2进制

减一做与

## Cpp

```cpp
class Solution {
public:
    bool isPowerOfTwo(int n) {
        if(n <= 0) return false;
        else return !(n & (n-1));
    }
};
```

## JavaScript

```JavaScript
/**
 * @param {number} n
 * @return {boolean}
 */
var isPowerOfTwo = function(n) {
    return (n > 0) && !(n & (n-1))
};
```