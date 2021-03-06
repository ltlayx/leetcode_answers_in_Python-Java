# Problem Definition of Maximum_Depth_of_Binary_Tree

Given a binary tree, find its maximum depth.

The maximum depth is the number of nodes along the longest path from the root node down to the farthest leaf node.

**Note:** A leaf is a node with no children.

**Example 1**:

    Input:
    Given binary tree [3,9,20,null,null,15,7],

        3
       / \
      9  20
        /  \
       15   7

    Output: 3

## Method

    Using recursion

    A binary tree's depth is either left_tree_depth +1 or right_tree_depth + 1

## Python Code

```python
class Solution:
    def maxDepth(self, root):
        """
        :type root: TreeNode
        :rtype: int
        """
        if root is None:
            return 0
        elif root.right is None and root.left is None:
            return 1
        leftdepth =  self.maxDepth(root.left)
        rightdepth = self.maxDepth(root.right)
        
        return (leftdepth if leftdepth >= rightdepth else rightdepth) +1
```

## Java Code

```java

```