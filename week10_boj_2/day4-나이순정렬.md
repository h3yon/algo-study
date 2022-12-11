# 나이순정렬

- 링크: https://www.acmicpc.net/problem/10814
- 난이도: Silver V

```
N = int(input())
arr = []

for i in range(N):
    age, name = input().split()
    arr.append((int(age), name))

arr[:] = sorted(arr, key=lambda x: x[0])
for a,b in arr:
    print(a,b)
```

나이순 다음 들어온 순서대로 정렬하는 것이다보니,  
이렇게 푸는 게 맞나 싶었는데 다행히 잘 풀렸다~
