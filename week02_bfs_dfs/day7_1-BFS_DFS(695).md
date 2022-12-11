# 695. Max Area of Island

- 난이도: Medium
- 문제 링크: https://leetcode.com/problems/max-area-of-island/
- 풀이시간: 40분

You are given an m x n binary matrix grid. An island is a group of 1's (representing land)  
connected 4-directionally (horizontal or vertical.) You may assume all four edges of the grid are surrounded by water.  

The area of an island is the number of cells with a value 1 in the island.  

Return the maximum area of an island in grid. If there is no island, return 0.  

 

Example 1:

```
Input: grid = [[0,0,1,0,0,0,0,1,0,0,0,0,0],[0,0,0,0,0,0,0,1,1,1,0,0,0],[0,1,1,0,1,0,0,0,0,0,0,0,0],[0,1,0,0,1,1,0,0,1,0,1,0,0],[0,1,0,0,1,1,0,0,1,1,1,0,0],[0,0,0,0,0,0,0,0,0,0,1,0,0],[0,0,0,0,0,0,0,1,1,1,0,0,0],[0,0,0,0,0,0,0,1,1,0,0,0,0]]
Output: 6
Explanation: The answer is not 11, because the island must be connected 4-directionally.
```

Example 2:

```
Input: grid = [[0,0,0,0,0,0,0,0]]
Output: 0
```

Constraints:

- m == grid.length
- n == grid[i].length
- 1 <= m, n <= 50
-  grid[i][j] is either 0 or 1.

## 풀어보기 & 회고

틀렸다.

```python
class Solution:
    def maxAreaOfIsland(self, grid: List[List[int]]) -> int:
        
        def dfs(x,y):
            if x < 0 or y < 0 or x >= len(grid) or y >= len(grid[0]):
                return
            if grid[x][y] == 1:
                grid[x][y] = 0
                dfs(x-1,y)
                dfs(x+1,y)
                dfs(x,y-1)
                dfs(x,y+1)
                return True
            return False
        
        count = 0
        for i in range(len(grid)):
            for j in range(len(grid[0])):
                if dfs(i,j) == True:
                    count += 1
        return count
```

<img width="613" alt="image" src="https://user-images.githubusercontent.com/46602874/192132534-a87f644d-ce3e-4027-a0b3-7a5ed40e2560.png">

왜 틀렸는지 모르겠답...  
문제를 보았을 때 한 덩어리씩 해서 count가 올라가도록 푸는 문제라고 생각했다.  

```python
class Solution:
    def maxAreaOfIsland(self, grid: List[List[int]]) -> int:
        
        def dfs(i,j,size):
            if i < 0 or j < 0 or i >= len(grid) or j >= len(grid[0]) or grid[i][j] != 1:
                return size
            grid[i][j] = 0
            size += 1
            size = dfs(i,j+1,size)
            size = dfs(i,j-1,size)
            size = dfs(i+1,j,size)
            size = dfs(i-1,j,size)
            return size
        # Find the maximum size count
        max_size = 0
        for i in range(len(grid)):
            for j in range(len(grid[0])):
                if grid[i][j] == 1:
                    max_size = max(max_size,dfs(i,j,0))
        return max_size
```

아 문제를 제대로 안 읽었나보다.  
알고보니까 한 덩어리씩 비교했을 때 가장 큰 사이즈를 구하는 문제였다ㅋㅋㅋㅋㅋ  
이건 내가 다시 한번 풀어봐야겠다!!
