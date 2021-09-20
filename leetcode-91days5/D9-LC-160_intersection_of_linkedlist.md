[LC 989. intersection of two linked lists](https://leetcode.com/problems/intersection-of-two-linked-lists/)


**python代码**
```
class Solution(object):
    def getIntersectionNode(self, headA, headB):
        """
        :type head1, head1: ListNode
        :rtype: ListNode
        """
        len1, len2 = 0, 0
        moveA, moveB = headA, headB
        while moveA:
            len1 += 1
            moveA = moveA.next
        while moveB:
            len2 += 1
            moveB = moveB.next
        if len1 < len2:
            for _ in range(len2 - len1):
                headB = headB.next
        else:
            for _ in range(len1 - len2):
                headA = headA.next
        while headA and headB and headA != headB:
            headA = headA.next
            headB = headB.next
        return headA

```

