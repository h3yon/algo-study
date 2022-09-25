# 733. Flood Fill

- 난이도: easy
- 문제 링크: https://leetcode.com/problems/flood-fill/
- 풀이시간: 40분

An image is represented by an m x n integer grid image where image[i][j] represents the pixel value of the image.  

You are also given three integers sr, sc, and color. You should perform a flood fill on the image starting from the pixel image[sr][sc].  

To perform a flood fill, consider the starting pixel, plus any pixels connected 4-directionally  
to the starting pixel of the same color as the starting pixel, plus any pixels connected 4-directionally  
to those pixels (also with the same color), and so on. Replace the color of all of the aforementioned pixels with color.  

Return the modified image after performing the flood fill.  

 

Example 1:

```
Input: image = [[1,1,1],[1,1,0],[1,0,1]], sr = 1, sc = 1, color = 2
Output: [[2,2,2],[2,2,0],[2,0,1]]
Explanation: From the center of the image with position (sr, sc) = (1, 1) (i.e., the red pixel), all pixels connected by a path of the same color as the starting pixel (i.e., the blue pixels) are colored with the new color.
Note the bottom corner is not colored 2, because it is not 4-directionally connected to the starting pixel.
```

Example 2:

```
Input: image = [[0,0,0],[0,0,0]], sr = 0, sc = 0, color = 0
Output: [[0,0,0],[0,0,0]]
Explanation: The starting pixel is already colored 0, so no changes are made to the image.
```

Constraints:

- m == image.length
- n == image[i].length
- 1 <= m, n <= 50
- 0 <= image[i][j], color < 216
- 0 <= sr < m
- 0 <= sc < n

# 풀어보기

```python
class Solution:
    def floodFill(self, image: List[List[int]], sr: int, sc: int, color: int) -> List[List[int]]:
        target = image[sr][sc]
        
        def dfs(x,y):
            if x < 0 or y < 0 or x >= len(image) or y >= len(image[0]):
                return
            if image[x][y] != target:
                return
            image[x][y] = color
            dfs(x+1,y)
            dfs(x-1,y)
            dfs(x,y+1)
            dfs(x,y-1)
        
        # main
        if target != color:
            dfs(sr, sc)
        
        return image
```

# 회고

처음에 이 문제를 봤을 때 이중 For문으로 생각했다.  
dfs에 많이 익숙해졌다고 생각했는데, 아직 가릭ㄹ은 먼 것 같다.  
문제 이해에 시간이 좀 걸렸고, 작성하는 데에도 좀 걸렸다.  
다시 한번 풀어보면 좋을 문제일 것 같다.
