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
var swapPairs = function(head) {
    
    if(head == null || head.next == null) {
        return head;
    }
    var p = new ListNode(null), q = new ListNode(null);
    p.next = head;
    q = head;
    
    while(q !== null && q.next !== null) {
        var tep = q.next.next;
        q.next.next = q;
        p.next = q.next;
        q.next = tep;
        p = q;
        q = q.next;
        
    }
    
    return p;
};
```
