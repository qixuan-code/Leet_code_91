[LC 768. Max Chunks To Make Sorted II](https://leetcode.com/problems/max-chunks-to-make-sorted-ii/)

**Ideas**
- Monotonic Stack
- key point:
   max[chunk[i-1]] <= min[chunk[i]] < max[chunk[i] <= min[chunk[i+1]]

**Comment**
Runtime: 69 ms, faster than 84.22%

**python code**
```
class Solution:
    def maxChunksToSorted(self, arr: List[int]) -> int:
        stack = []
        for a in arr:
            if stack and stack[-1]>a:
                store = stack[-1]
                while stack and stack[-1]>a:
                    stack.pop()
                stack.append(store)
            else:
                stack.append(a)
                
        return len(stack)
```

**复杂度分析**
- 时间复杂度：O(N)
- 空间复杂度：O(N)