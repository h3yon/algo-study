# 이진수

- 링크: https://www.acmicpc.net/problem/3460
- 난이도: 🥉 브론즈 3티어

양의 정수 n이 주어졌을 때, 이를 이진수로 나타냈을 때 1의 위치를 모두 찾는 프로그램을 작성하시오.  
최하위 비트(least significant bit, lsb)의 위치는 0이다.  

# 풀어보기

```python
T = int(input())
for _ in range(T):
    n = bin(int(input()))[2:]
    for idx, val in enumerate(n[::-1]):
        if val == '1':
            print(idx)
```

# 회고

항상 느끼는 거지만, reverse가 맨날 헷갈리는 것 같다.  
오늘도 즐거운 시간이었다~
