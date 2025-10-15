# 🧩 Maximum Depth of Binary Tree

## 📘 Problem Statement
Given the root of a binary tree, return its **maximum depth**.  
A binary tree's maximum depth is the number of nodes along the **longest path** from the root node down to the farthest leaf node.

---


---

## 💡 Explanation
The longest path from the root node (3) to the farthest leaf node is either:
- `3 → 9` → depth = 2  
- or `3 → 20 → 15` / `3 → 20 → 7` → depth = 3  

Hence, the **maximum depth = 3**.

---

## 🐍 Python Solution

```python
class TreeNode:
    def __init__(self, val=0, left=None, right=None):
        self.val = val
        self.left = left
        self.right = right

class Solution:
    def maxDepth(self, root: TreeNode) -> int:
        # Base case: if the tree is empty
        if not root:
            return 0
        
        # Recursively find depth of left and right subtrees
        left_depth = self.maxDepth(root.left)
        right_depth = self.maxDepth(root.right)
        
        # Return max depth between left and right, plus 1 for current node
        return 1 + max(left_depth, right_depth)



Approach:

    If the current node is None, return 0.

    Recursively compute the depth of the left and right subtrees.

    Add 1 for the current node level.

    Return the maximum of the two subtree depths.

⏱️ Time Complexity

O(n) — Every node is visited once.

💾 Space Complexity

O(h) — Due to recursive call stack, where h is the height of the tree.

