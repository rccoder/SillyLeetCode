# Odd-Even-Linked-List.md

Given a singly linked list, group all odd nodes together followed by the even nodes. Please note here we are talking about the node number and not the value in the nodes.

You should try to do it in place. The program should run in O(1) space complexity and O(nodes) time complexity.
```
Example:
Given 1->2->3->4->5->NULL,
return 1->3->5->2->4->NULL.
```
**Note:**
The relative order inside both the even and odd groups should remain as it was in the input. 
The first node is considered odd, the second node even and so on ...

## 解题思路

* 双指针
* 一个快一个
* 插入

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
var oddEvenList = function(head) {
    var p = head;
    var q = head;
    while(p) {
        q = q.next;
        
        if(q === null || q.next === null)  break;
        
        var np = p.next, nq = q.next;
        
        q.next = nq.next;
        p.next = nq;
        nq.next = np;
        
        p = p.next;
        
    }
    return head;
};
```

## Cpp

```cpp
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 */
class Solution {
public:
    ListNode* oddEvenList(ListNode* head) {
        ListNode *p = head;
        ListNode *q = head;
        while(q) {
            
            q = q->next;
            if(!q || !(q->next)) {
                break;
            }
            
            ListNode *np = p->next, *nq = q->next;
            
            q->next = nq->next;
            p->next = nq;
            nq->next = np;
            
            p = p->next;
            
        }
        
        return head;
    }
};
```
