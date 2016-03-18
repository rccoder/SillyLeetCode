# Min Stack
Design a stack that supports push, pop, top, and retrieving the minimum element in constant time.

+ push(x) -- Push element x onto stack.
+ pop() -- Removes the element on top of the stack.
+ top() -- Get the top element.
+ getMin() -- Retrieve the minimum element in the stack.

## JavaScript

``` javascript
/**
 * @constructor
 */
var MinStack = function() {
    this.data = [];
};

/**
 * @param {number} x
 * @returns {void}
 */
MinStack.prototype.push = function(x) {
    this.data.push(x);
};

/**
 * @returns {void}
 */
MinStack.prototype.pop = function() {
    var l = this.data.length;
    this.data = this.data.slice(0, l-1);
};

/**
 * @returns {number}
 */
MinStack.prototype.top = function() {
    return this.data[this.data.length-1];
};

/**
 * @returns {number}
 */
MinStack.prototype.getMin = function() {
    var l = this.data.length;
    var min = this.data[0];
    for(var i = 1; i < l; i ++) {
        min = this.data[i] < min ? this.data[i] : min;
    }
    return min;
};
```
