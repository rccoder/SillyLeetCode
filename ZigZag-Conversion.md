ZigZag Conversion
===

The string "PAYPALISHIRING" is written in a zigzag pattern on a given number of rows like this: (you may want to display this pattern in a fixed font for better legibility)
```
P   A   H   N
A P L S I I G
Y   I   R
```
And then read line by line: `"PAHNAPLSIIGYIR"`
Write the code that will take a string and make this conversion given a number of rows:
```
string convert(string text, int nRows);
```
convert("PAYPALISHIRING", 3) should return "PAHNAPLSIIGYIR".

## 解题思路

## Cpp
```cpp
class Solution {
public:
    string convert(string s, int numRows) {
        if(numRows == 1) return s;
        
        string result;
        int l = 2 * numRows - 2;
        for(int i = 0; i < numRows; i++) {
            for(int j = i; j < s.length(); j += l) {
                result.append(1, s[j]);
                if(i != 0 && i != numRows - 1) {
                    int tep = j + l - 2 * i;
                    if(tep < s.length()) {
                        result.append(1, s[tep]);
                    }
                }
            }
        }
        return result;
    }
   
};
```