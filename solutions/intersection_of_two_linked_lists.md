# Intersection of Two Linked Lists

https://leetcode.com/problems/intersection-of-two-linked-lists/

```python
class Solution:
    def getIntersectionNode(self, headA: ListNode, headB: ListNode) -> ListNode:
        if not headB or not headA:
            return
        p = headA
        q = headB
        while p != q:
            p = p.next
            q = q.next
            if p is q:
                break
            if not p:
                p = headB
            if not q:
                q = headA
        return p
```
