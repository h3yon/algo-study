# 숫자카드2

- 링크: https://www.acmicpc.net/problem/10816
- 난이도: Silver IV

아래는 틀렸던 풀이이다.  
계속 시간초과가 나는 부분이 문제점이었다.  

```
import sys
from collections import Counter 

N = int(input())
N_arr = list(map(int, sys.stdin.readline().split()))
M = int(input())
M_arr = list(map(int, sys.stdin.readline().split()))

answer = []
for i in M_arr:
    if i in N_arr:
        print(Counter(N_arr)[i], end=' ')
    else:
        print(0, end=' ')

```

핵심은 counter를 하나하나 하는 것보다는  
위에 써서 재활용해야되는 부분이었다.  
아래처럼 해서 시간초과나지 않고 풀 수 있었다~

```
import sys
from collections import Counter

N = int(sys.stdin.readline())
N_arr = list(map(int, sys.stdin.readline().split()))
counter = Counter(N_arr)

M = int(sys.stdin.readline())
M_arr = list(map(int, sys.stdin.readline().split()))

for i in M_arr:
    print(counter[i], end = ' ')
```
