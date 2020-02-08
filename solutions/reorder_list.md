# Reorder List

https://leetcode.com/problems/reorder-list/submissions/

```python
class Solution:
    def reorderList(self, head: ListNode) -> None:
        if not head:
            return
        reversed_list_head = self.split_and_reverse_last_half(head)
        while reversed_list_head:
            current_next = head.next
            current_reversed_next = reversed_list_head.next
            head.next = reversed_list_head
            reversed_list_head.next = current_next
            reversed_list_head = current_reversed_next
            head = current_next

    def get_list_lenght(self, head):
        len = 0
        while head:
            len += 1
            head = head.next
        return len

    def split_and_reverse_last_half(self, head):
        for _ in range(self.get_list_lenght(head) // 2):
            head = head.next
        reversed_list_head = head.next
        head.next = None
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