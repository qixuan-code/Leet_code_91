[LC 104. maxium depth of a binary tree](https://leetcode.com/problems/maximum-depth-of-binary-tree/)


**python代码**
```
class Solution:
    def maxDepth(self, root: Optional[TreeNode]) -> int:
 
        if root is None:
            return 0
        else:
            left_height = self.maxDepth(root.left)
            right_height = self.maxDepth(root.right)

            return 1+ max(left_height,right_height)
```

**复杂度分析**
- 时间复杂度：O(N)
- 空间复杂度：O(1)