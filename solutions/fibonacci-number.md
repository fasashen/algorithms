# 509. Fibonacci Number

https://leetcode.com/problems/fibonacci-number/

### Recursive
```python
class Solution:
    def fib(self, N: int) -> int:
        if N == 0:
            return 0
        elif N == 1:
            return 1
        else:
            return self.fib(N - 1) + self.fib(N - 2)
```

### Recursive w/ Memoization
```python
class Solution:
    def __init__(self, *args, **kwargs):
        self.cache = {}
        
    def fib(self, N: int) -> int:
        if N == 0:
            return 0
        elif N == 1:
            return 1
        else:
            if N not in self.cache:
                self.cache[N] = self.fib(N - 1) + self.fib(N - 2)
            return self.cache[N]
```

### Iterative
```python
class Solution:  
    def fib(self, N: int) -> int:
        table = [0,1,1]
        if N > 2:
            for i in range(N-2): 
                table.append(table[-1] + table[-2])
        return table[N]
```
