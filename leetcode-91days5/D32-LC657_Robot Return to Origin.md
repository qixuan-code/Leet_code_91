[LC 657. Robot Return to Origin](https://leetcode.com/problems/robot-return-to-origin/)

**Ideas**
- convert list to nums


**comment**
74 ms, faster than 34.88%


**python代码**
```
class Solution:
    def judgeCircle(self, moves: str) -> bool:
        x = y = 0
        for i in moves:
            if i == 'R':
                x += 1
            elif i == 'L':
                x -= 1
            elif i == 'U':
                y += 1
            else:
                y -= 1
        
        return True if y == 0 and x == 0 else False
```

**复杂度分析**
- 时间复杂度：O(N)
- 空间复杂度：O(1)