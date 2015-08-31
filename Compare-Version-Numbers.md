Compare Version Numbers
===
Compare two version numbers version1 and version2.

If version1 > version2 return 1, if version1 < version2 return -1, otherwise return 0.

You may assume that the version strings are non-empty and contain only digits and the `.` character.
The `.` character does not represent a decimal point and is used to separate number sequences.
For instance, `2.5` is not "two and a half" or "half way to version three", it is the fifth second-level revision of the second first-level revision.

Here is an example of version numbers ordering:
```
0.1 < 1.1 < 1.2 < 13.37
```
## 解题思路

Python操作字符串，比较简单

## Python
```Python
class Solution(object):
    def compareVersion(self, version1, version2):
        """
        :type version1: str
        :type version2: str
        :rtype: int
        """
        v1 = version1.split('.')
        v2 = version2.split('.')
        
        v1Len = len(v1)
        v2Len = len(v2)
        for i in range(max(v1Len, v2Len)):
            v1Tmp = 0
            v2Tmp = 0
            if i < v1Len:
                v1Tmp = int(v1[i])
            if i < v2Len:
                v2Tmp = int(v2[i])
            if(v1Tmp < v2Tmp):
                return -1
            if(v1Tmp > v2Tmp):
                return 1
        return 0
```
