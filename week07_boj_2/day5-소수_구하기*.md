# 소수 구하기

- 링크: https://www.acmicpc.net/problem/1929
- 난이도: Silver III

## 문제
M이상 N이하의 소수를 모두 출력하는 프로그램을 작성하시오.

## 입력

첫째 줄에 자연수 M과 N이 빈 칸을 사이에 두고 주어진다. (1 ≤ M ≤ N ≤ 1,000,000) M이상 N이하의 소수가 하나 이상 있는 입력만 주어진다.

```
3 16
```

## 출력
한 줄에 하나씩, 증가하는 순서대로 소수를 출력한다.

```
3
5
7
11
13
```

## 풀어보기

```python
import math

n,m = map(int, input().split())

def is_prime(num):
    if num < 2:
        return False
    for i in range(2, int(math.sqrt(num))+1):
        if num % i == 0:
            return False
    return True
    
for i in range(n, m+1):
    if is_prime(i) == True:
        print(i)
```

순간 가물가물했다..  
소수찾기 잘 기억해놔야겠다!
