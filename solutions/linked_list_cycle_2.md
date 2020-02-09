# Linked List Cycle II

https://leetcode.com/problems/linked-list-cycle-ii/submissions/

```python
class Solution:
    p = None
    q = None
    pos = None
    
    def detectCycle(self, head: ListNode) -> ListNode:
        self.p, self.q = head, head
        self.pos = head
        c = 0
        N = None
        while self.p and self.p.next and self.q.next and self.q.next.next:
            c += 1
            self.p = self.p.next
            self.q = self.q.next.next
            if N:
                self.pos = self.pos.next
            if self.p is self.pos:
                return self.pos
            if self.p is self.q:
                N = c
```
