Count Primes 
===
Count the number of prime numbers less than a non-negative number, n.

## 解题思路

n^2过不了，用筛法

## Cpp
```cpp
class Solution {
public:
    int countPrimes(int n) {
        vector<bool> flag(n, true);
        flag[0] = false, flag[1] = false;
        for (int i = 0; i < sqrt(n); ++i) {
            if (flag[i]) {
                for (int j = i*i; j < n; j += i) {
                    flag[j] = false;
                }    
            }    
        }
        return count(flag.begin(), flag.end(), true);
    }
};
```
