[LC 989. Add to Array-Form of Integer](https://leetcode-cn.com/problems/add-to-array-form-of-integer/)

**思路**
- 把num list转化成数字
- 数字和k相加
- 相加的和转化成list

**python代码**
```class Solution:
    def addToArrayForm(self, num: List[int], k: int) -> List[int]:
        n = len(num)
        true_number = 0
        result = []
        if k == 0 and len(num) == 1:
            return num
        for i in range(n):
            true_number = true_number + num[i]*10**(n-i-1)

        add_up = true_number + k
        while add_up:
            result.append(add_up%10)
            add_up = add_up//10

        return result[::-1]
```

**复杂度分析**
- 时间复杂度：O(N)
- 空间复杂度：O(N)