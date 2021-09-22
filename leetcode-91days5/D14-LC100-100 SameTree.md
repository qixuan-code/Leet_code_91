[LC 100. Same Tree](https://leetcode.com/problems/same-tree/)

**Ideas**
DFS
挖个坑，周末学习队列和BFS的解法
**comment**
Runtime:  24 ms, faster than 96.22% 


**python代码**
```
class Solution:
    def isSameTree(self, p: Optional[TreeNode], q: Optional[TreeNode]) -> bool:
        if not p and not q:
            return True
        elif not p or not q:
            return False
        elif p.val != q.val:
            return False
        return self.isSameTree(p.left,q.left) and self.isSameTree(p.right,q.right)
```

**复杂度分析**
- 时间复杂度：O(N)
- 空间复杂度：O(N)