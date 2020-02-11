# Remove Nth Node From End of List

https://leetcode.com/problems/remove-nth-node-from-end-of-list/

```python
class Solution:
    def removeNthFromEnd(self, head: ListNode, n: int) -> ListNode:
        if not head:
            return
        l = self.get_list_length(head)
        return self.remove_nth(head, l - n + 1)
    
    def get_list_length(self, head):
        c = 0
        while head:
            c += 1
            head = head.next
        return c
    
    def remove_nth(self, head, n):
        c = 0
        prev = None
        node = head
        while node:
            c += 1
            if n == c:
                if not prev:
                    return node.next
                prev.next = node.next
                break
            prev = node
            node = node.next
        return head
```
