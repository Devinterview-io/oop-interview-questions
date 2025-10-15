# 🧩 Maximum Depth of Binary Tree

## 📘 Problem Statement
Given the root of a binary tree, return its **maximum depth**.  
A binary tree's maximum depth is the number of nodes along the **longest path** from the root node down to the farthest leaf node.


---
// Definition for a binary tree node
class TreeNode {
    int val;
    TreeNode left;
    TreeNode right;

    TreeNode(int val) {
        this.val = val;
        this.left = null;
        this.right = null;
    }
}

class Solution {
    public int maxDepth(TreeNode root) {
        // Base case: if the tree is empty
        if (root == null) {
            return 0;
        }

        // Recursively find depth of left and right subtrees
        int leftDepth = maxDepth(root.left);
        int rightDepth = maxDepth(root.right);

        // Return max depth between left and right, plus 1 for current node
        return 1 + Math.max(leftDepth, rightDepth);
    }
}



Approach:

    If the current node is None, return 0.

    Recursively compute the depth of the left and right subtrees.

    Add 1 for the current node level.

    Return the maximum of the two subtree depths.

⏱️ Time Complexity

O(n) — Every node is visited once.

💾 Space Complexity

O(h) — Due to recursive call stack, where h is the height of the tree.

