# 단지번호붙이기

- 링크: https://www.acmicpc.net/problem/2667
- 난이도: Silver 1

## 문제

<그림 1>과 같이 정사각형 모양의 지도가 있다.  
1은 집이 있는 곳을, 0은 집이 없는 곳을 나타낸다.  
철수는 이 지도를 가지고 연결된 집의 모임인 단지를 정의하고, 단지에 번호를 붙이려 한다.  
여기서 연결되었다는 것은 어떤 집이 좌우, 혹은 아래위로 다른 집이 있는 경우를 말한다.  
대각선상에 집이 있는 경우는 연결된 것이 아니다.  
<그림 2>는 <그림 1>을 단지별로 번호를 붙인 것이다.  
지도를 입력하여 단지수를 출력하고, 각 단지에 속하는 집의 수를 오름차순으로 정렬하여 출력하는 프로그램을 작성하시오.

<img width="409" alt="image" src="https://user-images.githubusercontent.com/46602874/207612609-1f542f4e-3e07-4321-81aa-a382e60ff691.png">


## 입력

첫 번째 줄에는 지도의 크기 N(정사각형이므로 가로와 세로의 크기는 같으며 5≤N≤25)이 입력되고, 그 다음 N줄에는 각각 N개의 자료(0혹은 1)가 입력된다.

```python
7
0110100
0110101
1110101
0000111
0100000
0111110
0111000
```

## 출력

첫 번째 줄에는 총 단지수를 출력하시오. 그리고 각 단지내 집의 수를 오름차순으로 정렬하여 한 줄에 하나씩 출력하시오.

```
3
7
8
9
```

## 풀어보기

```python
from collections import deque

N = int(input())
arr = [list(map(int, input())) for _ in range(N)]
visited = [[False] * N for _ in range(N)]

dx = [1,-1,0,0]
dy = [0,0,1,-1]

def bfs(x,y):
    queue = deque([(x,y)])
    visited[x][y] = True
    tmp = 1
    while queue:
        x,y = queue.popleft()
        for i in range(4):
            nx = x + dx[i]
            ny = y + dy[i]
            if 0 <= nx < N and 0 <= ny < N and arr[nx][ny] != 0 and visited[nx][ny] == False:
                visited[nx][ny] = True
                tmp += 1
                queue.append((nx,ny))
    return tmp

cnt, answers = 0, []
for i in range(N):
    for j in range(N):
        if arr[i][j] != 0 and visited[i][j] == False:
            cnt += 1
            answers.append(bfs(i,j))

print(cnt)
for i in sorted(answers):
    print(i)
```

오 한번에 맞췄다.  
하루 안 풀었다고 순간 가물가물했는데, 꾸준히 풀어야겠다,,
