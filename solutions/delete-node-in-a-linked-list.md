# Delete Node in a Linked List

https://leetcode.com/problems/delete-node-in-a-linked-list/

```python
class Solution:
    def deleteNode(self, node):
        node.val , node.next = node.next.val, node.next.next
```
