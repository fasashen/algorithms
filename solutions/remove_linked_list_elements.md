# Remove Linked List Elements

https://leetcode.com/problems/remove-linked-list-elements/

```python
class Solution:
    def removeElements(self, head: ListNode, val: int) -> ListNode:
        prev = None
        node = head
        while node:
            if node.val == val:
                if prev:
                    prev.next = node.next
                else:
                    head = node.next
                node = node.next
            else:
                prev = node
                node = node.next
        return head

```