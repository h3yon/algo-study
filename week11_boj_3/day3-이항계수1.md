# 이항계수1

- 링크: https://www.acmicpc.net/problem/11050
- 난이도: Bronze I

## 문제

자연수 \(N\)과 정수 \(K\)가 주어졌을 때 이항 계수 
\(\binom{N}{K}\)를 구하는 프로그램을 작성하시오.

## 입력
첫째 줄에 \(N\)과 \(K\)가 주어진다. (1 ≤ \(N\) ≤ 10, 0 ≤ \(K\) ≤ \(N\))

```
5 2
```

## 출력
 
\(\binom{N}{K}\)를 출력한다.

```
10
```

## 풀어보기

```python
n, k = map(int, input().split())
tmp = 1
target = n

for i in range(k):
    tmp *= target
    target -= 1

print(tmp // k)
```

위처럼 풀었는데 틀렸다ㅠ  
`n! / (n-r)! r!`을 원하는 것으로 보인다.  

```python
import math

n, k = map(int, input().split())
answer = math.factorial(n) // (math.factorial(k)*math.factorial(n-k))
print(answer)
```

흠,, 이렇게 푸는 걸 원하셨던 걸로 보인다!
