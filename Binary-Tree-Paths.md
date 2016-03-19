# Binary Tree Paths

Given a binary tree, return all root-to-leaf paths.

For example, given the following binary tree:

```
   1
 /   \
2     3
 \
  5
```
All root-to-leaf paths are:

["1->2->5", "1->3"]

## 解题思路

* 递归，顺便传路径

## JavaScript

``` javascript
/**
 * Definition for a binary tree node.
 * function TreeNode(val) {
 *     this.val = val;
 *     this.left = this.right = null;
 * }
 */
/**
 * @param {TreeNode} root
 * @return {string[]}
 */
var result = [];
var binaryTreePaths = function(root) {
    if(root !== null) {
        fuck(root, root.val.toString());
    }
    return result;
};
var fuck = function(root, s) {
    if(root.left === null && root.right === null) {
        result.push(s)
    }
    if(root.left !== null) {
        fuck(root.left, s + '->' + root.left.val);
    }
    if(root.right !== null) {
        fuck(root.right, s + '->' + root.right.val);
    }
}
```
