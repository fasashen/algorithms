# Palindrome Linked List

https://leetcode.com/problems/palindrome-linked-list/

```python
class Solution:
    def isPalindrome(self, head: ListNode) -> bool:
        if not head or not head.next:
            return True
        
        # Ищем середину
        p = head
        q = head
        while q and q.next:
            q = q.next.next
            if q and not q.next:
                p.next, p = None, p.next
                head2 = p.next
                break  # Нечетное количество членов
            if not q:
                head2, p.next = p.next, None
                break
            p = p.next
        
        # Разворачиваем вторую половину списка 
        previous = None
        while head2:
            _next = head2.next
            head2.next = previous
            previous = head2
            if not _next:
                break
            head2 = _next
            
        # Сравниваем обе половины
        p1 = head
        p2 = head2
        while p1 and p2:
            if p1.val != p2.val:
                return False
            p1 = p1.next
            p2 = p2.next

        return True
```
