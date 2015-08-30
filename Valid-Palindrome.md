Valid Palindrome 
===
Given a string, determine if it is a palindrome, considering only alphanumeric characters and ignoring cases.

For example,

`"A man, a plan, a canal`: Panama" is a palindrome.

`"race a car"` is not a palindrome.

**Note:**

Have you consider that the string might be empty? This is a good question to ask during an interview.

For the purpose of this problem, we define empty string as valid palindrome.

## Cpp

```cpp
class Solution {
public:
    bool isPalindrome(string s) {
        if(s.size() == 0) return true;
        for(int i = 0; i < s.size(); i++) {
            s[i] = toupper(s[i]);
        }
        int low = 0, high = s.size()-1;
        while(low < high) {
            if((s[low] < 'A' || s[low] > 'Z') && (s[low] < '0' || s[low] > '9')) {
                low ++;
                continue;
            }
            if((s[high] < 'A' || s[high] > 'Z') && (s[high] < '0' || s[high] > '9')) {
                high --;
                continue;
            }
            if(s[low] == s[high]) {
                low ++;
                high --;
            } else {
                return false;
            }
        }
        return true;
    }
};
```
