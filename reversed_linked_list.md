# 206. Reverse Linked List

https://leetcode.com/problems/reverse-linked-list/

### Iterative
```python
class Solution:
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

### Recursive
```python
class Solution:
    def reverseList(self, head: ListNode) -> ListNode:
        return self._reverse(None, head) if head else None

    def _reverse(self, prev, node):
        _next = node.next
        node.next = prev
        return self._reverse(node, _next) if _next else node

```
