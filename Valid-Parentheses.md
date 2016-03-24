# Valid Parentheses

Given a string containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.

The brackets must close in the correct order, "()" and "()[]{}" are all valid but "(]" and "([)]" are not.

## JavaScript

``` javascript
/**
 * @param {string} s
 * @return {boolean}
 */
 
function Stack() {
    this.data = [];
    this.top = 0;
}

Stack.prototype.push = function(e) {
    this.data.push(e);
    this.top++;
}

Stack.prototype.pop = function() {
    if (!this.empty()) {
        this.data.splice(-1, 1);
        this.top --;   
    }
}

Stack.prototype.peek = function() {
    return this.data[this.data.length-1];
}

Stack.prototype.empty = function() {
    return this.top === 0 ? true : false;
}

var isValid = function(s) {
    var sArray = s.split("");
    
    var tep = new Stack();
    
    for(var i = 0; i < sArray.length; i++) {
        
        if(sArray[i] === '[') {
            tep.push(']');
        } else if(sArray[i] === '(') {
            tep.push(')');
        } else if(sArray[i] === '{') {
            tep.push('}');
        }
        
        if(sArray[i] === ']' || sArray[i] === ')' || sArray[i] === '}') {
            if(sArray[i] !== tep.peek()) {
                return false;
            } else {
                tep.pop();
            }
        }
    }
    
    if(tep.empty()) {
        return true;   
    } else {
        return false;
    }
};
```
