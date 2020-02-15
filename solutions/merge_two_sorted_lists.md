# Merge Two Sorted Lists

https://leetcode.com/problems/merge-two-sorted-lists

```python
class Solution:
    def mergeTwoLists(self, l1: ListNode, l2: ListNode) -> ListNode:
        if not l1 or not l2:
            return l1 or l2
        tail = None
        while l1 and l2:
            if l1.val <= l2.val:
                min_node = l1
                l1 = l1.next
            else:
                min_node = l2
                l2 = l2.next
            if not tail:
                tail = min_node
                head = min_node
                continue
            tail.next = min_node
            tail = tail.next
        tail.next = l1 or l2
        return head
```
