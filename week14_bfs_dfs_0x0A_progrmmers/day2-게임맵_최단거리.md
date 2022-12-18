# 게임 맵 최단거리

- 링크: https://school.programmers.co.kr/learn/courses/30/lessons/1844
- 난이도: Level 2

## 문제 설명

ROR 게임은 두 팀으로 나누어서 진행하며, 상대 팀 진영을 먼저 파괴하면 이기는 게임입니다.  
따라서, 각 팀은 상대 팀 진영에 최대한 빨리 도착하는 것이 유리합니다.  
지금부터 당신은 한 팀의 팀원이 되어 게임을 진행하려고 합니다.  
다음은 5 x 5 크기의 맵에, 당신의 캐릭터가 (행: 1, 열: 1) 위치에 있고,  
상대 팀 진영은 (행: 5, 열: 5) 위치에 있는 경우의 예시입니다.

<img width="178" alt="image" src="https://user-images.githubusercontent.com/46602874/208281582-cd6a0a7a-68e8-46a3-95fb-95ea1b4bca5c.png">

위 그림에서 검은색 부분은 벽으로 막혀있어 갈 수 없는 길이며, 흰색 부분은 갈 수 있는 길입니다.  
캐릭터가 움직일 때는 동, 서, 남, 북 방향으로 한 칸씩 이동하며, 게임 맵을 벗어난 길은 갈 수 없습니다.  
아래 예시는 캐릭터가 상대 팀 진영으로 가는 두 가지 방법을 나타내고 있습니다.  
첫 번째 방법은 11개의 칸을 지나서 상대 팀 진영에 도착했습니다.  

<img width="178" alt="image" src="https://user-images.githubusercontent.com/46602874/208281586-de45da45-6bb3-447e-b554-327df5b77670.png">

두 번째 방법은 15개의 칸을 지나서 상대팀 진영에 도착했습니다.

<img width="178" alt="image" src="https://user-images.githubusercontent.com/46602874/208281599-034e1862-77bd-4c30-8f78-209fbc168bc8.png">

위 예시에서는 첫 번째 방법보다 더 빠르게 상대팀 진영에 도착하는 방법은 없으므로, 이 방법이 상대 팀 진영으로 가는 가장 빠른 방법입니다.  
만약, 상대 팀이 자신의 팀 진영 주위에 벽을 세워두었다면 상대 팀 진영에 도착하지 못할 수도 있습니다.  
예를 들어, 다음과 같은 경우에 당신의 캐릭터는 상대 팀 진영에 도착할 수 없습니다.  

<img width="178" alt="image" src="https://user-images.githubusercontent.com/46602874/208281607-1082d6c1-3e9e-49ce-9b65-28acf000f59b.png">

게임 맵의 상태 maps가 매개변수로 주어질 때,  
캐릭터가 상대 팀 진영에 도착하기 위해서 지나가야 하는 칸의 개수의 최솟값을 return 하도록 solution 함수를 완성해주세요.  
단, 상대 팀 진영에 도착할 수 없을 때는 -1을 return 해주세요.

## 제한사항

- maps는 n x m 크기의 게임 맵의 상태가 들어있는 2차원 배열로, n과 m은 각각 1 이상 100 이하의 자연수입니다.
- n과 m은 서로 같을 수도, 다를 수도 있지만, n과 m이 모두 1인 경우는 입력으로 주어지지 않습니다.
- maps는 0과 1로만 이루어져 있으며, 0은 벽이 있는 자리, 1은 벽이 없는 자리를 나타냅니다.
- 처음에 캐릭터는 게임 맵의 좌측 상단인 (1, 1) 위치에 있으며, 상대방 진영은 게임 맵의 우측 하단인 (n, m) 위치에 있습니다.

## 입출력 예
|maps|answer|
|--|--|
|[[1,0,1,1,1],[1,0,1,0,1],[1,0,1,1,1],[1,1,1,0,1],[0,0,0,0,1]]|11|
|[[1,0,1,1,1],[1,0,1,0,1],[1,0,1,1,1],[1,1,1,0,0],[0,0,0,0,1]]|-1|

### 입출력 예 설명

#### 입출력 예 #1

주어진 데이터는 다음과 같습니다.

<img width="178" alt="image" src="https://user-images.githubusercontent.com/46602874/208281622-35e4cf2b-cbe8-47c6-8766-e5c4687c60da.png">

캐릭터가 적 팀의 진영까지 이동하는 가장 빠른 길은 다음 그림과 같습니다.

<img width="178" alt="image" src="https://user-images.githubusercontent.com/46602874/208281626-9f2addf5-d001-4586-af05-3ec6c5ae866b.png">

따라서 총 11칸을 캐릭터가 지나갔으므로 11을 return 하면 됩니다.

#### 입출력 예 #2

문제의 예시와 같으며, 상대 팀 진영에 도달할 방법이 없습니다. 따라서 -1을 return 합니다.

## 풀어보기

```python
from collections import deque

def solution(maps):
    
    dx = [1,-1,0,0]
    dy = [0,0,1,-1]
    n,m = len(maps), len(maps[0])
    dist = [[-1 for _ in range(m)] for _ in range(n)]
    
    def bfs(x ,y):
        queue = deque([(x,y)])
        dist[x][y] = 1
        while queue:
            x,y = queue.popleft()
            for i in range(4):
                nx = x + dx[i]
                ny = y + dy[i]
                if 0 <= nx < n and 0 <= ny < m:
                    if dist[nx][ny] == -1 and maps[nx][ny] == 1:
                        dist[nx][ny] = dist[x][y] + 1
                        queue.append((nx,ny))
    
    bfs(0,0)
    answer = dist[n-1][m-1]
    
    return answer
```

처음에 visited로 풀었을 때에는 틀렸다ㅎㅎ  
visited로 풀 때 maps[nx][ny] = maps[x][y] + 1로 풀었었는데,  
애초에 값이 1로 되어있었기 때문에 진짜 1일 때도 고려해야 함을 알았다.  
이 부분에서 좀 막혔는데, 애초에 dist로 다 -1로 채운 후,  
dist 처음 시작할 때 1로 하고 dist[nx][ny] = dist[x][y] + 1   
해주면 된다는 걸 알았다.  
처음 dist n과 m의 위치를 헷갈렸는데, 좀더 정신 차리고 풀어야겠다

                        dist[nx][ny] = dist[x][y] + 1
