# Word Pattern
Given a pattern and a string str, find if str follows the same pattern.

Here follow means a full match, such that there is a bijection between a letter in pattern and a non-empty word in str.

```
Examples:
pattern = "abba", str = "dog cat cat dog" should return true.
pattern = "abba", str = "dog cat cat fish" should return false.
pattern = "aaaa", str = "dog cat cat dog" should return false.
pattern = "abba", str = "dog dog dog dog" should return false.
```

**Notes:**

You may assume pattern contains only lowercase letters, and str contains lowercase letters separated by a single space.

## 解题思路

* hashtable
* 对比

## JavaScript

``` javascript
/**
 * @param {string} pattern
 * @param {string} str
 * @return {boolean}
 */
var wordPattern = function(pattern, str) {
    var patternArray = pattern.split("");
    var strArray = str.split(" ");
    
    if(strArray.length !== patternArray.length) return false;
    
    var hashp = {}, hashs = {};
    
    var count = 0;
    
    for(var i = 0; i < patternArray.length; i++) {
        if(hashp[patternArray[i]] === undefined) {
            hashp[patternArray[i]] = strArray[count];
        }
        if(hashs[strArray[count]] === undefined) {
            hashs[strArray[count]] = patternArray[i];
        }
        
        if(hashs[strArray[count]] != patternArray[i] || hashp[patternArray[i]] != strArray[count]) {
            return false;
        }
        count ++;
    }
    return true;
};
```
