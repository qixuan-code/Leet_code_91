[LC 347. Top K Frequent Elements](https://leetcode-cn.com/problems/top-k-frequent-elements/)

**Ideas**
- use hashmap to store frequency count
- sort by frequency and get top k number


**comment**
Runtime: 40 ms beat 75%


**python代码**
```
class Solution:
    def topKFrequent(self, nums: List[int], k: int) -> List[int]:

        hashmap = dict()

        for num in nums:
            hashmap[num] = 0

        for num in nums:
            if num in hashmap:
                hashmap[num] +=1
                
        sort_map = dict(sorted(hashmap.items(), key = lambda item:item[1],reverse=True))
        i = 0
        result = []
        for num, count in enumerate(sort_map):
            if i < k:
                result.append(count)
                i = i+1
            else:
                break

        return result
```
```
# o(N) 解法
nums = [1,1,1,3,2,2]
import collections
counter = collections.Counter(nums)
n = len(nums)
buckets = [[] for _ in range(n)]
for key in counter:
    buckets[counter[key]-1].append(key)
    
res = []
for i in range(n-1,-1,-1):
    for b in buckets[i]:
        res.append(b)
        if len(res) >= k:
            break
```
```
# o(N) 解法
nums = [1,1,1,3,2,2]
import collections
counter = collections.Counter(nums)
n = len(nums)
buckets = [[] for _ in range(n)]
for key in counter:
    buckets[counter[key]-1].append(key)
    
res = []
for i in range(n-1,-1,-1):
    for b in buckets[i]:
        res.append(b)
        if len(res) >= k:
            break
```
**复杂度分析**
- 时间复杂度：O(nlogn + 2n + k)
- 空间复杂度：O(n)