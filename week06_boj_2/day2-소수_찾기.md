# 소수 찾기

- 링크: https://www.acmicpc.net/problem/1978
- 난이도: 🥈실버 4티어

주어진 수 N개 중에서 소수가 몇 개인지 찾아서 출력하는 프로그램을 작성하시오.

## 입력

첫 줄에 수의 개수 N이 주어진다. N은 100이하이다. 다음으로 N개의 수가 주어지는데 수는 1,000 이하의 자연수이다.

```
4
1 3 5 7
```

## 출력

주어진 수들 중 소수의 개수를 출력한다.

```
3
```

## 풀어보기

이건 좀 충격적이다ㅜㅜ
내가 소수찾기를 까먹다니..

```python
import math

def is_prime(num):
    if num < 2:
        return False
    for i in range(2, int(math.sqrt(num)+1)):
        if num % i == 0:
            return False
    return True

N = int(input())
arr = list(map(int, input().split()))
answer = 0

for num in arr:
    if is_prime(num) == True:
        answer += 1

print(answer)
```

주의할 부분은 `int(math.sqrt(num)+1)` 이다.  
float로 되기 때문에 int를 해주어야 하는 것이다.  
꼭 기억해두자.!
근데 `math.sqrt` 대신 그냥 다 돌면 어떻게 될까?

```python
n = int(input())
nums = list(map(int, input().split()))
answer = 0

for i in nums:
    cnt = 0 
    if(i == 1):
        continue
    for j in range(2, i+1):
        if(i % j == 0):
            cnt += 1
    if(cnt == 1):
        answer += 1
print(answer)
```

<img width="763" alt="image" src="https://user-images.githubusercontent.com/46602874/197373696-a15202db-85b6-49b9-9c31-90f09f869046.png">

그래도 별 차이는 없다.  
하지만 비교해야되는 수가 많아질 때 내가 푼 방식이 좋은 것으로 알고 있다.  
정 기억이 안 난다면 `int(math.sqrt(num)+1)` 대신 `num+1`로 다 도는 방법도 있다.!
