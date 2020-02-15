# Reorder List

https://leetcode.com/problems/reorder-list/submissions/

```python
class Solution:
    def reorderList(self, head: ListNode) -> None:
        if not head:
            return
        reversed_list_head = self.splitReverseHalf(head)
        while reversed_list_head:
            current_next = head.next
            current_reversed_next = reversed_list_head.next
            head.next = reversed_list_head
            reversed_list_head.next = current_next
            reversed_list_head = current_reversed_next
            head = current_next

    def splitReverseHalf(self, head):
        p = head
        q = head
        while q and q.next:
            q = q.next.next
            p = p.next
        reversed_list_head = p.next
        p.next = None
        reversed_list_head = self.reverseList(reversed_list_head)
        return reversed_list_head

    def reverseList(self, head: ListNode) -> ListNode:
        if not head:
            return
        previous = None
        while True:
            _next = head.next
            head.next = previous
            previous = head
            if not _next:
                return head
            head = _next
```