Longest Common Prefix
===
Write a function to find the longest common prefix string amongst an array of strings.

## 解题思路

找一系列字符串里面共有的，最小的

## Cpp
```cpp
class Solution {
public:
    string longestCommonPrefix(vector<string>& strs) {
        if(strs.size() == 0) return "";
        string prefix = strs[0];
        for(int i = 0; i < strs.size(); i++) {
            int j = 0;
            while(j < prefix.size() && j < strs[i].size() && strs[i][j] == prefix[j]) j++;
            if(j == 0) return "";
            prefix = prefix.substr(0, j);
        }
        return prefix;
    }
};
```
## Python
```python
class Solution(object):
    def longestCommonPrefix(self, strs):
        """
        :type strs: List[str]
        :rtype: str
        """
        if(len(strs) == 0):
            return ""
        
        prefix = strs[0]
        
        for i in range(len(strs)):
            j = 0
            while(j < len(prefix) and j < len(strs[i]) and strs[i][j] == prefix[j]):
                j += 1
            if(j == 0):
                return ""
            else:
                prefix = prefix[0: j]
        
        return prefix
```
