[LC 876. Middle of the Linked List](https://leetcode.com/problems/middle-of-the-linked-list/)

**Ideas**
- method 1: get the depth of the linked list and return to half of it
- method 2: slow and fast pointer


**python代码**
```
class Solution:
    def middleNode(self, head: Optional[ListNode]) -> Optional[ListNode]:
        depth = 1
        hea = head
        result = head
        while hea.next:
            depth = depth + 1
            hea = hea.next


        start = depth//2 +1

        for i in range(start-1):
            result = result.next
            
        return result
```
```
class Solution:
    def middleNode(self, head: Optional[ListNode]) -> Optional[ListNode]:
        slow = head
        fast = head
        while fast and fast.next:
            fast = fast.next.next
            slow = slow.next
            
        return slow
```

**复杂度分析**
- 时间复杂度：O(N)
- 空间复杂度：O(1)