[LC 142. Linked List Cycle II](https://leetcode.com/problems/linked-list-cycle-ii/)

**Ideas**
- use hashtable to store the listnode

**comment**
Runtime: Runtime: 86 ms, faster than 11.71% 

**python代码**
```
class Solution:
    def detectCycle(self, head: ListNode) -> ListNode:
        d = dict()
        i=0
        while head:
            d[head] = i
            i = i + 1
            head = head.next
            if head in d:
                break
                
        return head
        
```

**复杂度分析**
- 时间复杂度：O(N)
- 空间复杂度：O(N)