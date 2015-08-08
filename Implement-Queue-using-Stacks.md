Implement Queue using Stacks
===

Implement the following operations of a queue using stacks.

* push(x) -- Push element x to the back of queue.

* pop() -- Removes the element from in front of queue.

* peek() -- Get the front element.

* empty() -- Return whether the queue is empty.

Notes:

* You must use only standard operations of a stack -- which means only push to top, peek/pop from top, size, and is empty operations are valid.

* Depending on your language, stack may not be supported natively. You may simulate a stack by using a list or deque (double-ended queue), as long as you use only standard operations of a stack.

* You may assume that all operations are valid (for example, no pop or peek operations will be called on an empty queue).

## 解题思路

维护两个栈-in out

push 到in

out空，in全部pop到out

out的top

## Cpp

```cpp
class Queue {
private:
    stack<int> inStack, outStack;
public:
    // Push element x to the back of queue.
    void push(int x) {
        inStack.push(x);
    }

    // Removes the element from in front of queue.
    void pop(void) {
        peek();
        outStack.pop();
    }

    // Get the front element.
    int peek(void) {
        if(outStack.empty()) {
            while(!(inStack.empty())) {
                outStack.push(inStack.top());
                inStack.pop();
            }
        }
        return outStack.top();
    }

    // Return whether the queue is empty.
    bool empty(void) {
        return inStack.empty() && outStack.empty();
    }
};
```

## Python

```python
class Queue:
    # initialize your data structure here.
    def __init__(self):
        self.inStack = []
        self.outStack = []

    # @param x, an integer
    # @return nothing
    def push(self, x):
        self.inStack.append(x)
    # @return nothing
    def pop(self):
        self.peek()
        self.outStack.pop()

    # @return an integer
    def peek(self):
        if not self.outStack:
            while self.inStack:
                self.outStack.append(self.inStack.pop())
        return self.outStack[-1]

    # @return an boolean
    def empty(self):
        return len(self.inStack) + len(self.outStack) == 0
        
```