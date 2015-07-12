Lowest Common Ancestor of a Binary Search Tree
===  

 Given a binary search tree (BST), find the lowest common ancestor (LCA) of two given nodes in the BST.

According to the definition of LCA on Wikipedia: “The lowest common ancestor is defined between two nodes v and w as the lowest node in T that has both v and w as descendants (where we allow a node to be a descendant of itself).”
```
        _______6______
       /              \
    ___2__          ___8__
   /      \        /      \
   0      _4       7       9
         /  \
         3   5
```
For example, the lowest common ancestor (LCA) of nodes 2 and 8 is 6. Another example is LCA of nodes 2 and 4 is 2, since a node can be a descendant of itself according to the LCA definition.

##简单思路

求二叉搜索树中给定两个节点的最近公共祖先（LCA）

从root开始，三种情况

两边，全左，全右

递归

##Cpp

```cpp
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode(int x) : val(x), left(NULL), right(NULL) {}
 * };
 */
class Solution
{
public:
    TreeNode* lowestCommonAncestor(TreeNode* root, TreeNode* p, TreeNode* q)
    {
        // two side
        if ((root->val - p->val) * (root->val - q->val) <= 0) {
            return root;
        }
        // one side
        else if (p->val < root->val) {
            return lowestCommonAncestor(root->left, p, q);
        } else {
            return lowestCommonAncestor(root->right, p, q);
        }

    }
};

```

##JavaScript

```javascript
/**
 * Definition for a binary tree node.
 * function TreeNode(val) {
 *     this.val = val;
 *     this.left = this.right = null;
 * }
 */
/**
 * @param {TreeNode} root
 * @param {TreeNode} p
 * @param {TreeNode} q
 * @return {TreeNode}
 */
var lowestCommonAncestor = function(root, p, q) {
    if((root.val - p.val) * (root.val - q.val) <= 0) {
        return root;
    } else if(root.val - p.val > 0) {
        return lowestCommonAncestor(root.left, p, q);
    } else {
        return lowestCommonAncestor(root.right, p, q);
    }
};
```