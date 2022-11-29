# 덱

- 링크: https://www.acmicpc.net/problem/10866
- 난이도: Silver IV

정수를 저장하는 덱(Deque)를 구현한 다음, 입력으로 주어지는 명령을 처리하는 프로그램을 작성하시오.

명령은 총 여덟 가지이다.

- push_front X: 정수 X를 덱의 앞에 넣는다.
- push_back X: 정수 X를 덱의 뒤에 넣는다.
- pop_front: 덱의 가장 앞에 있는 수를 빼고, 그 수를 출력한다. 만약, 덱에 들어있는 정수가 없는 경우에는 -1을 출력한다.
- pop_back: 덱의 가장 뒤에 있는 수를 빼고, 그 수를 출력한다. 만약, 덱에 들어있는 정수가 없는 경우에는 -1을 출력한다.
- size: 덱에 들어있는 정수의 개수를 출력한다.
- empty: 덱이 비어있으면 1을, 아니면 0을 출력한다.
- front: 덱의 가장 앞에 있는 정수를 출력한다. 만약 덱에 들어있는 정수가 없는 경우에는 -1을 출력한다.
- back: 덱의 가장 뒤에 있는 정수를 출력한다. 만약 덱에 들어있는 정수가 없는 경우에는 -1을 출력한다.

```
from collections import deque
import sys

N = int(sys.stdin.readline())
queue = deque([])

for i in range(N):
    cmd = sys.stdin.readline().split()
    if cmd[0] == 'push_back':
        queue.append(int(cmd[1]))
    elif cmd[0] == 'push_front':
        queue.appendleft(int(cmd[1]))
    elif cmd[0] == 'pop_front':
        try:
            print(queue.popleft())
        except:
            print(-1)
    elif cmd[0] == 'pop_back':
        try:
            print(queue.pop())
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

덱에서 기억할 건, appendleft, popleft만 기억하면 될 것으로 보인다  
시간초과가 나서 sys로 하니 맞습니다가 나왔다~
