# 207. Course Schedule

https://leetcode.com/problems/course-schedule/

```python
class Solution:
    def canFinish(self, numCourses: int, prerequisites: List[List[int]]) -> bool:
        self.graph = [[] for x in range(numCourses)]
        self.visit = [0 for x in range(numCourses)]
        for x, y in prerequisites:
            self.graph[x].append(y)
        for n in range(numCourses):
            if not self.dfs(n):
                return False
        return True

    def dfs(self, node):
        if self.visit[node] == 1:
            return True
        if self.visit[node] == -1:
            return False
        self.visit[node] = -1
        for n in self.graph[node]:
            if not self.dfs(n):
                return False
        self.visit[node] = 1
        return True
```
