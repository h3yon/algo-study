# 요세푸스 문제 0

- 링크: https://www.acmicpc.net/problem/11866
- 난이도: Silver V
  
요세푸스 문제는 다음과 같다.  

1번부터 N번까지 N명의 사람이 원을 이루면서 앉아있고, 양의 정수 K(≤ N)가 주어진다.  
이제 순서대로 K번째 사람을 제거한다. 한 사람이 제거되면 남은 사람들로 이루어진 원을 따라 이 과정을 계속해 나간다.  
이 과정은 N명의 사람이 모두 제거될 때까지 계속된다. 원에서 사람들이 제거되는 순서를 (N, K)-요세푸스 순열이라고 한다.  
예를 들어 (7, 3)-요세푸스 순열은 <3, 6, 2, 7, 5, 1, 4>이다.  

N과 K가 주어지면 (N, K)-요세푸스 순열을 구하는 프로그램을 작성하시오.  

## 풀어보기 

처음 아래처럼 풀었더니 틀렸다

```python
n,k = map(int, input().split())
arr = [i+1 for i in range(n)]
ans = []

while len(arr) >= k:
    left = arr[:k-1]
    right = arr[k:]
    ans.append(arr[k-1])
    arr.pop(k-1)
    arr[:] = right + left
ans += arr

print(str(ans).replace('[', '<').replace(']', '>')) 
```

솔직히 위에와 비슷한 느낌이긴 한데,  
아래가 더 효율적이긴 하다.  

```python
from collections import deque

n,k = map(int, input().split())
arr = deque([i+1 for i in range(n)])
ans = []

while arr:
    for _ in range(k-1):
        arr.append(arr.popleft())
    ans.append(arr.popleft())

print(str(ans).replace('[', '<').replace(']', '>'))
```

예전에 틀렸어서 한번 다시 풀어보았는데,  
다시 풀어보길 잘 한 것 같다.
