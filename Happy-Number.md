Happy Number
===

Write an algorithm to determine if a number is "happy".

A happy number is a number defined by the following process: Starting with any positive integer, replace the number by the sum of the squares of its digits, and repeat the process until the number equals 1 (where it will stay), or it loops endlessly in a cycle which does not include 1. Those numbers for which this process ends in 1 are happy numbers.

Example: **19** is a happy number
```
12 + 92 = 82
82 + 22 = 68
62 + 82 = 100
12 + 02 + 02 = 1
```
## 解题思路
放集合

## Cpp
```cpp
class Solution {
public:
    bool isHappy(int n) {
        set<int> SET;
        while(n != 1 && (SET.find(n) == SET.end())) {
            SET.insert(n);
            int sum = 0;
            while(n) {
                int tep = n % 10;
                sum += tep * tep;
                n /= 10;
            }
            n = sum;
        }
        return n == 1;
    }
};
```

## Python
```python
class Solution(object):
    def isHappy(self, n):
        """
        :type n: int
        :rtype: bool
        """
        SET = set()
        
        while(n != 1 and n not in SET):
            SET.add(n)
            sum = 0
            
            while(n):
                tep = n % 10
                sum += tep * tep
                n /= 10
            
            n = sum
        return n == 1
```
