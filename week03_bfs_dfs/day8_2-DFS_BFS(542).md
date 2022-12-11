# 542. 01 Matrix

- 난이도: Medium
- 링크: https://leetcode.com/problems/01-matrix/

Given an m x n binary matrix mat, return the distance of the nearest 0 for each cell.  

The distance between two adjacent cells is 1.  

 

Example 1:

![image](https://user-images.githubusercontent.com/46602874/193271015-528ab7ee-a789-406c-9a15-11a59ec6f4b3.png)

```
Input: mat = [[0,0,0],[0,1,0],[0,0,0]]
Output: [[0,0,0],[0,1,0],[0,0,0]]
```

Example 2:

![image](https://user-images.githubusercontent.com/46602874/193271056-ec9fa1ca-05ca-46aa-8041-5231a40b1493.png)

```
Input: mat = [[0,0,0],[0,1,0],[1,1,1]]
Output: [[0,0,0],[0,1,0],[1,2,1]]
 ```

Constraints:

- m == mat.length
- n == mat[i].length
- 1 <= m, n <= 104
- 1 <= m * n <= 104
- mat[i][j] is either 0 or 1.
- There is at least one 0 in mat.

# 회고

```python
from collections import deque

class Solution:
    def updateMatrix(self, mat: List[List[int]]) -> List[List[int]]:
        queue = deque()
        
        visited = set()
        for i in range(len(mat)):
            for j in range(len(mat[0])):
                if mat[i][j] == 0:
                    visited.add((i,j))
                    queue.append((i,j))
        
        while queue:
            x,y = queue.popleft()
            for direction in [(1,0),(-1,0),(0,1),(0,-1)]:
                _x, _y = x+direction[0], y+direction[1]
                if _x >= 0 and _x <= len(mat) -1 and _y >= 0 and _y <= len(mat[0]) -1 and (_x,_y) not in visited:
                        mat[_x][_y] = mat[x][y] + 1
                        visited.add((_x,_y))
                        queue.append((_x,_y))
        return mat
```

어렵다 while 문까지는 우리가 아는 BFS 문제인데,  
DP까지 혼합된 개념이다보니 혼란이 왔답,,  
코드로는 깔끔하지만 한번 더 풀어봐야 할 것 같다.  
