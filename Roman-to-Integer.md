Roman to Integer 
===

Given a roman numeral, convert it to an integer.

Input is guaranteed to be within the range from 1 to 3999.

## 解题思路

[WIKI](https://zh.wikipedia.org/wiki/%E7%BD%97%E9%A9%AC%E6%95%B0%E5%AD%97)


## Cpp

```cpp
class Solution {
private:
    int RConvertI(const char R) {
        switch(R){
            case 'I' : return 1;
            case 'V' : return 5;
            case 'X' : return 10;
            case 'L' : return 50;
            case 'C' : return 100;
            case 'D' : return 500;
            case 'M' : return 1000;
            default :  return 0;
        }
    }
public:
    int romanToInt(string s) {
        int result = 0;
        for(int i = 0; i < s.size(); i++) {
            int S1 = RConvertI(s[i]), S2 = RConvertI(s[i-1]);
            if(S1 > S2 && i >= 1) result += S1 - 2*S2;
            else result += S1;
        }
        return result;
    }
};
```
## Cpp

```cpp
class Solution {
private:
    
public:
    map<char, int> MAP = {
        {'I', 1},
        {'V', 5}, 
        {'X', 10},
        {'L', 50},
        {'C', 100},
        {'D', 500},
        {'M', 1000}
    };
    
    int romanToInt(string s) {
        int result = 0;
        for(int i = 0; i < s.size(); i++) {
            int S1 = MAP[s[i]], S2 = MAP[s[i-1]];
            if(S1 > S2 and i >= 1) result += S1 - 2*S2;
            else result += S1;
        }
        return result;
    }
};
```

## Python

```python
class Solution(object):
    def romanToInt(self, s):
        """
        :type s: str
        :rtype: int
        """
        map = {'I':1, 'V':5, 'X':10, 'L':50, 'C':100, 'D':500, 'M':1000}
        
        result = 0
        
        for i in range(len(s)):
            if(map[s[i]] > map[s[i-1]] and i >= 1):
                result += (map[s[i]]-2*map[s[i-1]])
            else:
                result += map[s[i]]
        return result
```
