# Sum of Left Leaves
---
- ## Question:
> Given the root of a binary tree, return the sum of all left leaves.
> 
> A leaf is a node with no children. A left leaf is a leaf that is the left child of another node.
---
- ## Example:
![alt](https://assets.leetcode.com/uploads/2021/04/08/leftsum-tree.jpg)
> Input: root = [3,9,20,null,null,15,7]
> 
> Output: 24
> 
> Explanation: There are two left leaves in the binary tree, with values 9 and 15 respectively.
---
- ## Solution:
**Code :**
```java
public class Solution {
    public int sumOfLeftLeaves(TreeNode root) {
        if (root == null) return 0;
        int sum = 0;
        if (root.left != null && root.left.left == null && root.left.right == null) {
            sum += root.left.val;
        } else {
            sum += sumOfLeftLeaves(root.left);
        }
        sum += sumOfLeftLeaves(root.right);
        return sum;
    }
}
