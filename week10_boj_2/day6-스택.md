# 스택

- 링크: https://www.acmicpc.net/problem/10828
- 난이도: Silver IV

정수를 저장하는 스택을 구현한 다음, 입력으로 주어지는 명령을 처리하는 프로그램을 작성하시오.  

명령은 총 다섯 가지이다.  

- push X: 정수 X를 스택에 넣는 연산이다.
- pop: 스택에서 가장 위에 있는 정수를 빼고, 그 수를 출력한다. 만약 스택에 들어있는 정수가 없는 경우에는 -1을 출력한다.
- size: 스택에 들어있는 정수의 개수를 출력한다.
- empty: 스택이 비어있으면 1, 아니면 0을 출력한다.
- top: 스택의 가장 위에 있는 정수를 출력한다. 만약 스택에 들어있는 정수가 없는 경우에는 -1을 출력한다.

```
import sys
N = int(sys.stdin.readline().strip())
arr = []

for i in range(N):
    cmd = sys.stdin.readline().strip().split()
    if cmd[0] == 'push':
        arr.append(int(cmd[1]))
    elif cmd[0] == 'top':
        try:
            print(arr[-1])
        except:
            print(-1)
    elif cmd[0] == 'size':
        print(len(arr))
    elif cmd[0] == 'pop':
        try:
            print(arr.pop())
        except:
            print(-1)
    elif cmd[0] == 'empty':
        if len(arr) < 1:
            print(1)
        else:
            print(0)
```

시간초과가 나서 sys를 썼더니  
시간초과 나지 않고 잘 풀리는 걸 볼 수 있었다~!
