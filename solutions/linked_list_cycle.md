# Linked List Cycle

https://leetcode.com/problems/linked-list-cycle/submissions/

Идею подсмотрел

```python
class Solution:
    def hasCycle(self, head: ListNode) -> bool:
        p, q = head, head
        while p and p.next and q.next and q.next.next:
            p = p.next
            q = q.next.next
            if p is q:
                return True
        return False
```
