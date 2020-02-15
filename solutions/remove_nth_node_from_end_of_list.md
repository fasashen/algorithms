# Remove Nth Node From End of List

https://leetcode.com/problems/remove-nth-node-from-end-of-list/

```python
class Solution:
    def removeNthFromEnd(self, head: ListNode, n: int) -> ListNode:
        if not head:
            return
        p = None
        q = head
        offset = 0
        while q and q.next:
            q = q.next
            offset += 1
            if offset >= n:
                if not p:
                    p = head
                else:
                    p = p.next
        if not p:
            return head.next
        p.next = p.next.next
        return head
```
