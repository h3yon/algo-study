# 피보나치

- 링크: https://www.acmicpc.net/problem/1003
- 난이도: Silver III

```python
import sys

def fibo(n):
    global zero, one
    if n == 0:
        zero += 1
        return 0
    elif n == 1:
        one += 1
        return 1
    else:
        return fibo(n-1) + fibo(n-2)

T = int(sys.stdin.readline())
for i in range(T):
    N = int(sys.stdin.readline())
    zero, one = 0,0
    
    fibo(N)
    print(zero, one)
```

저번주에 계속 풀었지만 틀렸던 문제이다.  
검색해서 계속 이해하려고 했다.  
시중의 다른 분들의 답을 보면서 도저히 이해를 못했는데,  
오늘 그나마 이해를 할 수 있었다!  
  
피보나치의 식을 보자.  

```
fibo(n-1) + fibo(n-2)
```

보통 피보나치 식은 위와 같다.  
그러니까 fibo(n)의 0과 1의 갯수는 아래와 같다.  

```
[fibo(n)의 0과 1의 갯수] = [fibo(n-1)의 0과 1의 갯수] + [fibo(n-2)의 0과 1의 갯수]
```

그래서 차례대로 0 1 2를 보았을 때 zeros와 ones는 아래와 같다.

```python
def fibo(N):
    zeros=[1,0,1]
    ones=[0,1,1]
    if N >= 3:
        for i in range(2,N):
            zeros.append(zeros[i-1] + zeros[i])
            ones.append(ones[i-1] + ones[i])
    print(zeros[N],ones[N])
    
T = int(input())
for _ in range(T):
    N = int(input())
    fibo(N)
```

