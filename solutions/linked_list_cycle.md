# Linked List Cycle

https://leetcode.com/problems/linked-list-cycle/submissions/

Идею подсмотрел

```python
class Solution:
    p = None
    q = None
    
    def hasCycle(self, head: ListNode) -> bool:
        self.p, self.q = head, head
        while self.p and self.p.next and self.q.next and self.q.next.next:
            self.p = self.p.next
            self.q = self.q.next.next
            if self.p is self.q:
                return True
        return False
```
