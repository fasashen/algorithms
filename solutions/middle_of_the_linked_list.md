# Middle of the Linked List

https://leetcode.com/problems/middle-of-the-linked-list/

```python
class Solution:
    def middleNode(self, head: ListNode) -> ListNode:
        p = head
        q = head
        while q and q.next:
            q = q.next.next
            p = p.next
        return p
```
