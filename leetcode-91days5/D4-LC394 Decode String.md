[LC 394. Decode String](https://leetcode.com/problems/decode-string/)

没有思路，把答案默写了一遍

**python代码**
```
class Solution:
    def decodeString(self, s: str) -> str:
        stack = [] 
        for i in s:
            if i == ']':
                strs = ''
                repeat_number = ''
                while stack and stack[-1] !='[':
                    strs = stack.pop()+strs #the sequence here is very important
                stack.pop() #pop out'[]'
        
                while stack and stack[-1].isdigit():
                    repeat_number = stack.pop() +repeat_number 
                    
                stack.append(int(repeat_number)*strs) #has to append to stack,3[a2[c]]
            
            else:
                stack.append(i)
        return "".join(stack)
        


```

**复杂度分析**
- 时间复杂度：O(N)
- 空间复杂度：O(N)