[kth pair distance](https://binarysearch.com/problems/Kth-Pair-Distance)

**Ideas**
- use two pointers to calculate number of pair distance smaller than certain distance(diff)
- binary search: find a distance so that there are number of k distances smaller than it. 

**python代码**
```
nums.sort()
def no_greater_than(diff):
    for j in range(1,len(nums)):
        res = i = 0
        while nums[j] - nums[i] > diff:
            i += 1
        res += j-i
    return res

l,r = 0, nums[-1]-nums[0]
while l<=r:
    mid = l+(r-l)//2
    if no_great_than(mid) > k:
        right = mid - 1
    else:
        left = mid + 1
return left

```

**复杂度分析**
- 时间复杂度：O(nlogn)