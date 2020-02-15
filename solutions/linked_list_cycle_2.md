# Linked List Cycle II

https://leetcode.com/problems/linked-list-cycle-ii/submissions/

```python
class Solution:
    def detectCycle(self, head: ListNode) -> ListNode:
        p = head
        q = head
        pos = head
        loop_found = False
        while p and p.next and q.next and q.next.next:
            p = p.next
            q = q.next.next
            pos = pos.next if loop_found else pos
            loop_found = True if loop_found or p is q else False
            if p is pos:
                return pos
```
