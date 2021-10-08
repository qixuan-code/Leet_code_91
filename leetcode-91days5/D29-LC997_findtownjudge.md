[LC 997.Find the Town Judge](https://leetcode-cn.com/problems/find-the-town-judge/)

**Ideas**
- 法官在每个数组的第一个元素中应该不存在
- 法官在每个数组的第二个元素中应该有n-1个


**python代码**
```
class Solution:
    def findJudge(self, n: int, trust: List[List[int]]) -> int:
        truster =list(set(map(lambda x:x[0], trust)))
        trustee = list(map(lambda x:x[1],trust))

        total_people = [i for i in range(1,n+1)]
        for element in truster:
            if element in total_people:
                total_people.remove(element)

        a = collections.Counter(trustee)

        if len(total_people) == 0:
            return -1
        else: 
            for i in total_people:
                if a[i] == n-1:
                    return i 
                else:
                    return -1
```

**复杂度分析**
- 时间复杂度：O(N)
