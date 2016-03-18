
# Reverse Linked List

Reverse a singly linked list.

**Hint:**

A linked list can be reversed either iteratively or recursively. Could you implement both?

## 解题思路

* 双指针
* [比较详细的文章介绍](http://blog.csdn.net/feliciafay/article/details/6841115)

## JavaScript
``` javascript
/**
 * Definition for singly-linked list.
 * function ListNode(val) {
 *     this.val = val;
 *     this.next = null;
 * }
 */
/**
 * @param {ListNode} head
 * @return {ListNode}
 */
var reverseList = function(head) {
    var p = new ListNode(null);
    var q = new ListNode(null);
    if(head == null || head.next == null) {
        return head;
    }
    p = head;
    q = head.next;
    head.next = null;
    while(q) {
        var t = q.next;
        q.next = p;
        p = q;
        q = t;
    }
    
    return p;
};
```
