[LC 989. Add to Array-Form of Integer](https://leetcode-cn.com/problems/add-to-array-form-of-integer/)

**思路**
- 把num list转化成数字
- 数字和k相加
- 相加的和转化成list

**comment**
Runtime: 5116 ms beat 5%
Memory Usage: 15.3 MB beat 87%

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


**tricks**
- convert integar to list 
``` 
     k = list(map(int,str(k)))
     divmod(12,10) = (1,2)
     range(start,stop,step) 左开右闭
     list = [int] + list
```

```
num = [2,1,5]
K=806
    
def addToArrayForm(num, K):
    carry = 0

    for i in range(len(num)-1,-1,-1):
        num[i]= (carry + num[i] + K % 10) % 10
        carry = (carry + num[i] + K % 10) // 10  #this is wrong, as num[i] changes
        K = K // 10
        
    result = []
    carry = carry +K
    
    while carry: 
        result = [carry%10] + result 
        carry = carry // 10
        
    return result + A
```

```
def addToArrayForm(A, K):
    carry = 0
    for i in range(len(A) - 1, -1, -1):
        A[i], carry = (carry + A[i] + K % 10) % 10, (carry + A[i] + K % 10) // 10
        K //= 10
    B = []
    # 如果全部加完还有进位，需要特殊处理。 比如 A = [2], K = 998
    carry = carry + K
    while carry:
        B = [(carry) % 10] + B
        carry //= 10
    return B + A

```