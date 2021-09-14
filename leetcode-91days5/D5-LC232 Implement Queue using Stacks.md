[232. Implement Queue using Stacks](https://leetcode.com/problems/implement-queue-using-stacks/)

**Ideas**
- this problem asks to implement queue(FIFO) by two stacks. I use one stack for enqueue function and the other for dequeue.

**comment**
Runtime: Runtime: 38 ms, faster than 18.90% 

**python代码**
```
class MyQueue:

    def __init__(self):
        """
        Initialize your data structure here.
        """
        self.enqueue_stack = []
        self.dequeue_stack = []
        

    def push(self, x: int) -> None:
        """
        Push element x to the back of queue.
        """
        self.enqueue_stack.append(x)
            
  

    def pop(self) -> int:
        """
        Removes the element from in front of queue and returns that element.
        """
        if self.dequeue_stack == []:
            
            while self.enqueue_stack:
                self.dequeue_stack.append(self.enqueue_stack.pop())
            
        return self.dequeue_stack.pop()

    def peek(self) -> int:
        """
        Get the front element.
        """
        if self.dequeue_stack == []:
            return self.enqueue_stack[0]
        else:
            return self.dequeue_stack[-1]

    def empty(self) -> bool:
        """
        Returns whether the queue is empty.
        """
        return self.enqueue_stack == [] and self.dequeue_stack == []
        
```

**复杂度分析**
- 时间复杂度：O(N)
- 空间复杂度：O(N)]

**Ideas**
- convert list to nums
- add it up
- switch it to list

**comment**
Runtime: 5116 ms beat 5%
Memory Usage: 15.3 MB beat 87%

**python代码**
```
```

**复杂度分析**
- 时间复杂度：O(N)
- 空间复杂度：O(N)