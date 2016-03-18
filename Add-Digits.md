# Add Digits

Given a non-negative integer num, repeatedly add all its digits until the result has only one digit.

For example:

Given num = 38, the process is like: 3 + 8 = 11, 1 + 1 = 2. Since 2 has only one digit, return it.

Follow up:

Could you do it without any loop/recursion in O(1) runtime?

**Hint:**

A naive implementation of the above process is trivial. Could you come up with other methods?

## 解题思路

* 最笨的办法，递归。然后打败了 js 写的 9% 的代码...
* 做演算，发现规律
```
10 1
11 2
12 3
13 4
...
99 18 9
```
(in - 1) % 9 + 1

## JavaScript

``` javascript
/**
 * @param {number} num
 * @return {number}
 */
var addDigits = function(num) {
    var numArray = (num).toString().split("");
    var numLength = numArray.length;
    var sum = 0;
    for(var i = 0; i < numLength; i++) {
        sum += parseInt(numArray[i]);
    }
    if(sum < 10) {
        return sum;   
    } else {
        return addDigits(sum);
    }
};
```

## JavaScript

``` javascript
/**
 * @param {number} num
 * @return {number}
 */
var addDigits = function(num) {
    return (num-1) % 9 + 1;
};
```
