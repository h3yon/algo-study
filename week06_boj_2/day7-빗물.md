# 빗물

- 링크: https://www.acmicpc.net/problem/14719
- 난이도: 골드5

```
input = input()
H, W = map(int,input().split())
block = list(map(int,input().split()))
answer = 0

for i in range(1, W-1):
    left_max = max(block[:i])
    right_max = max(block[i+1:])
    lower_max = min(left_max, right_max)
    if block[i] < lower_max:
        answer += lower_max - block[i]

print(answer)
```

For문을 돌면서 가장 높은 부분을 찾자.  
그 기준 left와 right max를 구하고자 한다.  
그중 낮은 max보다 더 채워질리는 없으니까  
현재 블럭이 lower_max보다 작다면, 답에 lower_max에서 해당 블럭 값을 빼어  
답을 구한다.
