# Remove Nth Node From End of List

Given a linked list, remove the nth node from the end of list and return its head.

For example,

   Given linked list: 1->2->3->4->5, and n = 2.

   After removing the second node from the end, the linked list becomes 1->2->3->5.
   
**Note:**

Given n will always be valid.

Try to do this in one pass.

## 解题思路

中间相差n的指针

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
 * @param {number} n
 * @return {ListNode}
 */
var removeNthFromEnd = function(head, n) {

    var p = new ListNode(null), q = new ListNode(null);
    p = head;
    q = head;
    for(var i = 0; i < n; i++) {
        q = q.next;
    }
    if(q === null) {
        return head.next;
    }
    while(q.next !== null) {
        p = p.next;
        q = q.next;
    }
    p.next = p.next.next;
    return head;
};
```
