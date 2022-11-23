# 큐

- 링크: https://www.acmicpc.net/problem/10845
- 난이도: Silver IV

정수를 저장하는 큐를 구현한 다음, 입력으로 주어지는 명령을 처리하는 프로그램을 작성하시오.  

명령은 총 여섯 가지이다.  

- push X: 정수 X를 큐에 넣는 연산이다.
- pop: 큐에서 가장 앞에 있는 정수를 빼고, 그 수를 출력한다. 만약 큐에 들어있는 정수가 없는 경우에는 -1을 출력한다.
- size: 큐에 들어있는 정수의 개수를 출력한다.
- empty: 큐가 비어있으면 1, 아니면 0을 출력한다.
- front: 큐의 가장 앞에 있는 정수를 출력한다. 만약 큐에 들어있는 정수가 없는 경우에는 -1을 출력한다.
- back: 큐의 가장 뒤에 있는 정수를 출력한다. 만약 큐에 들어있는 정수가 없는 경우에는 -1을 출력한다.

```
from collections import deque

N = int(input())
queue = deque([])

for i in range(N):
    cmd = input().split()
    if cmd[0] == 'push':
        queue.append(int(cmd[1]))
    elif cmd[0] == 'pop':
        try:
            print(queue.popleft())
        except:
            print(-1)
    elif cmd[0] == 'size':
        print(len(queue))
    elif cmd[0] == 'empty':
        if len(queue) < 1:
            print(1)
        else:
            print(0)
    elif cmd[0] == 'front':
        try:
            print(queue[0])
        except:
            print(-1)
    elif cmd[0] == 'back':
        try:
            print(queue[-1])
        except:
            print(-1)
```

큐를 사용하는 문제여서 재밌었다~  
이제 다음주면 level2가 끝!!
