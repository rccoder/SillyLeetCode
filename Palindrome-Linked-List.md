Palindrome Linked List 
===

Given a singly linked list, determine if it is a palindrome.

##解题思路

两个指针

##Cpp

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
    bool isPalindrome(ListNode* head) {
        if (!head || !(head -> next)) return true;
        ListNode* slow = head;
        ListNode* fast = head;
        while (fast && fast -> next) {
            slow = slow -> next;
            fast = fast -> next -> next;
        }
        if (fast) {
            slow -> next = reverseList(slow -> next);
            slow = slow -> next;
        }
        else slow = reverseList(slow);
        while (slow) {
            if (head -> val != slow -> val)
                return false;
            head = head -> next;
            slow = slow -> next;
        }
        return true;
    }
private:
    ListNode* reverseList(ListNode* node) {
        ListNode* pre = NULL;
        while (node) {
            ListNode* next = node -> next;
            node -> next = pre;
            pre = node;
            node = next;
        }
        return pre;
    }
};
```
