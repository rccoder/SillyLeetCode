Merge Two Sorted Lists
===
Merge two sorted linked lists and return it as a new list. The new list should be made by splicing together the nodes of the first two lists.

##解题思路

新建一个

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
    ListNode* mergeTwoLists(ListNode* l1, ListNode* l2) {
        if(!l1 || !l2) return l1 != NULL ? l1 : l2;
        ListNode *result;
        ListNode *T = result;
        
        while(l1 != NULL && l2 != NULL) {
            if(l1->val > l2->val) {
                result->next = l2;
                l2 = l2->next;
            } else {
                result->next = l1;
                l1 = l1->next;
            }
            result = result->next;
        }
        
        if(l1) result->next = l1;
        if(l2) result->next = l2;
    
        
        return T->next;
    }
};
```

## Python
```python
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution(object):
    def mergeTwoLists(self, l1, l2):
        """
        :type l1: ListNode
        :type l2: ListNode
        :rtype: ListNode
        """
        if(not l1):
            return l2
        if(not l2):
            return l1

        tmp = ListNode(0)
        T = tmp
        
        while(l1 and l2):
            if(l1.val > l2.val):
                tmp.next = l2
                l2 = l2.next
            else:
                tmp.next = l1
                l1 = l1.next
            tmp = tmp.next
        
        if(l1):
            tmp.next = l1
        if(l2):
            tmp.next = l2
            
        return T.next
```
