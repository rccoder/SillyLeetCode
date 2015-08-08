Valid Anagram
===
Given two strings s and t, write a function to determine if t is an anagram of s.

For example,

s = "anagram", t = "nagaram", return true.
s = "rat", t = "car", return false.

Note:

You may assume the string contains only lowercase alphabets.

## 解题思路

判断每个字符出现的次数

先排序，然后看是否相等

## Cpp

```cpp
class Solution {
public:
    bool isAnagram(string s, string t) {
        if(s.size() != t.size()) return false;
        // 每个字母出现的次数
        int tep[26] = {0};
        for(int i = 0; i < s.size(); i++) {
            tep[s[i]-'a']++;
        }
        for(int i = 0;  i < t.size(); i++) {
            tep[t[i]-'a']--;
            if(tep[t[i]-'a'] < 0) return false;
        }
        return true;
    }
};
```

## Python

```python
class Solution:
    # @param {string} s
    # @param {string} t
    # @return {boolean}
    def isAnagram(self, s, t):
        return sorted(s) == sorted(t);
```