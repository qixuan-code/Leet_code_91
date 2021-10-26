[Number of Operations to Decrement Target to Zero](https://binarysearch.com/problems/Number-of-Operations-to-Decrement-Target-to-Zero)

**Ideas**
- the question can be converted: find a substring whose sum equals to sum(nums) - target with max lenghth.

**python代码**
```
class Solution:
    def solve(self, nums, target):
        if sum(nums) == target: return len(nums)
        sum_remain = sum(nums)-target
        left, right =0,0
        max_len = 0
        cur_sum = 0
        for right, value in enumerate(nums):
            cur_sum += value
            while cur_sum > sum_remain and left < right:
                cur_sum -= nums[left]
                left += 1
            if cur_sum == sum_remain:
                max_len = max(max_len, right-left + 1)

        return len(nums)-max_len if max_len !=0 else -1
```

**复杂度分析**
- 时间复杂度：O(N)
