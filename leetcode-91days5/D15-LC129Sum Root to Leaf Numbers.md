[LC 129. Sum Root to Leaf Numbers](https://leetcode.com/problems/sum-root-to-leaf-numbers/)

**Ideas**
dfs

**comment**
Runtime: 28 ms, faster than 88.46%

**python代码**
```
class Solution:

    def sumNumbers(self, root: Optional[TreeNode]) -> int:
        
        def dfs(root,presum):
            if root == None:
                return 0
            presum = presum*10 + root.val
            if root.left == None and root.right == None:
                return presum
            else:
                return dfs(root.left, presum) + dfs(root.right,presum)
    
        return dfs(root, 0)
```

**复杂度分析**
- 时间复杂度：O(N)
- 空间复杂度：O(N)