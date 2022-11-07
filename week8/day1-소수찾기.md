# 소수 찾기

- 링크: https://www.acmicpc.net/problem/1978
- 난이도: Silver V

주어진 수 N개 중에서 소수가 몇 개인지 찾아서 출력하는 프로그램을 작성하시오.

## 입력
첫 줄에 수의 개수 N이 주어진다. N은 100이하이다. 다음으로 N개의 수가 주어지는데 수는 1,000 이하의 자연수이다.

## 예제 입력 1 

```
4
1 3 5 7
```

## 출력

주어진 수들 중 소수의 개수를 출력한다.

## 예제 출력 1 

```
3
```

## 풀어보기

```python
import math

n = int(input())
arr = list(map(int, input().split()))

def is_prime(num):
    if num < 2:
        return False
    for i in range(2, int(math.sqrt(num))+1):
        if num % i == 0:
            return False
    return True

answer = 0
for i in arr:
    if is_prime(i) == True:
        answer += 1

print(answer)
```

완벽하게 외웠담!


