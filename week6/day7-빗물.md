# 빗물

- 링크: https://www.acmicpc.net/problem/14719
- 난이도: 골드5

```
input = input()
H, W = map(int,input().split())
block = list(map(int,input().split()))
answer = 0

for i in range(1, W-1):
    left = max(block[:i])
    right = max(block[i+1:])
    _min = min(left, right)
    if _min > block[i]:
        answer += _min - block[i]

print(answer)
```

For문을 돌면서 가장 높은 부분을 찾자.
그 기준 left와 right max를 구하고자 한다.
구한 max끼리 비교하여 _min인 경우 비교하여 답을 구하자
