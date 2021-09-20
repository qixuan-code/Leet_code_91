[LC 61. Rotate List](https://leetcode.com/problems/rotate-list/)

**Ideas**
- Slow fast pointer 
- k means that the gap between slow pointer and fast pointer

**comment**
Runtime: Runtime: 66 ms, faster than 6.74%

**python代码**
```
class Solution:
    def rotateRight(self, head: Optional[ListNode], k: int) -> Optional[ListNode]:
        if k ==0 or not head or not head.next:
            return head
        #calculate the length of the linked list
        cur = head
        length = 1
        
        while cur.next != None:
            cur = cur.next
            length += 1
            
        k = k%length
        
        fast = head
        slow = head
        for i in range(k):
            fast = fast.next
        while fast.next != None:
            fast = fast.next
            slow = slow.next
        
        
        fast.next = head
        head = slow.next
        slow.next = None
        
        return head
```

**复杂度分析**
- 时间复杂度：O(N)
- 空间复杂度：O(1)