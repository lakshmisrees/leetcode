# Diameter of Binary Tree (LeetCode 543)

## 📌 Problem Statement
Given the root of a binary tree, return the **diameter of the tree**.

The **diameter of a binary tree** is the length of the longest path between any two nodes in a tree.  
This path **may or may not pass through the root**.

The length of a path is represented by the **number of edges** between the nodes.

---

## 💡 Approach (Optimized DFS)

The key idea is:
- The diameter at any node is the sum of:
  - height of left subtree
  - height of right subtree
- While calculating the height of each node, we update the maximum diameter.
- Each node is visited exactly once.

---

## ⚙️ Algorithm
1. Use a recursive DFS function to compute the height of each node.
2. At every node:
   - Calculate left and right subtree heights.
   - Update the diameter using `leftHeight + rightHeight`.
3. Return the maximum diameter found.

---

## 🚀 Java Implementation

```java
class Solution {
    int diameter = 0;

    public int diameterOfBinaryTree(TreeNode root) {
        height(root);
        return diameter;
    }

    private int height(TreeNode node) {
        if (node == null) return 0;

        int leftHeight = height(node.left);
        int rightHeight = height(node.right);

        // Update diameter (number of edges)
        diameter = Math.max(diameter, leftHeight + rightHeight);

        // Return height of current node
        return Math.max(leftHeight, rightHeight) + 1;
    }
}
