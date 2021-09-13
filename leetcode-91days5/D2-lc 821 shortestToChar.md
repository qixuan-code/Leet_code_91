[821. Shortest Distance to a Character](https://leetcode.com/problems/shortest-distance-to-a-character/)

**Ideas**
- store position information of the target character
- calculate the absolute distance between each element in the string and position of target character
- get the minumum 

**comment**
Runtime: 146 ms beat 5%

**python代码**
```
class Solution:
    def shortestToChar(self, s: str, c: str) -> List[int]:
        temp = []
        res = []
        for i in range(len(s)):
            if s[i] == c:
                temp.append(i)
        
        for j in range(len(s)):
            a = [abs(x-j) for x in temp]
            res.append(min(a))
            
        return res
```
**复杂度分析**
- 时间复杂度：O(N^2+N)
- 空间复杂度：O(N)


```
class Solution:
    def shortestToChar(self, s: str, c: str) -> List[int]:
        res= []
        prev = float('-inf')
        for i,char in enumerate(s):
            if char ==c:
                prev = i
            res.append(abs(i-prev))
        
        prev = float('-inf')
        for k in range(len(s)-1, -1,-1):
            if s[k] == c:
                prev = k
            res[k]=(min(res[k],abs(prev-k)))
            
        return res
```

**复杂度分析**
- Time complexity: O(2N)
- Space complexity: O(N)