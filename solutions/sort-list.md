# 148. Sort List

https://leetcode.com/problems/sort-list/

### Recursive
```python
class Solution:
    def sortList(self, head: ListNode) -> ListNode:
        if head and head.next is not None:
            l_head = head
            r_head = self.split_list(head)
            
            l = self.sortList(l_head)
            r = self.sortList(r_head)
            
            if l.val < r.val:
                head = l
                l = l.next
            else:
                head = r
                r = r.next
            p = head
    
            while l and r:
                if l.val < r.val:
                    p.next = l
                    l = l.next
                else:
                    p.next = r
                    r = r.next
                
                p = p.next
            p.next = l if l else r
        return head

    def split_list(self, head: ListNode) -> ListNode:
        p = head
        q = head
        while True:
            q = q.next.next
            if not q or not q.next:
                split_head = p.next
                p.next = None
                return split_head
            p = p.next
```
