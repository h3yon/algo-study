# BFS 복습

```python
graph = [
    [],
    [2,3,8],
    [1,7],
    [1,4,5],
    [3,5],
    [3,4],
    [7],
    [2,6,8],
    [1,7]
]

visited = [False] * 9

bfs(graph, 1, visited)

# 출력: 1 2 3 8 7 4 5 6
```

처음 BFS를 공부하면서 풀었던 문제이다. 
이만큼 익숙해졌으니 한번 더 풀어보고 DFS로 넘어가면 좋을 것 같다!  

```python
from collections import deque
graph = [
    [],
    [2,3,8],
    [1,7],
    [1,4,5],
    [3,5],
    [3,4],
    [7],
    [2,6,8],
    [1,7]
]

visited = [False] * 9

# 여기 추가
def bfs(graph, i, visited):
    queue = deque([i])
    visited[i] = True
    while queue:
        tmp = queue.popleft()
        print(tmp, end=' ')
        for i in graph[tmp]:
            if visited[i] == False:
                visited[i] = True
                queue.append(i)
        

bfs(graph, 1, visited)

# 출력: 1 2 3 8 7 4 5 6
```

흑흑 아직 어렵다,,  
역시 BFS는 꾸준히 하나씩 풀어야겠다..
