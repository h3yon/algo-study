# 수 정렬하기3

- 링크: https://www.acmicpc.net/problem/10989
- 난이도: Bronze I

N개의 수가 주어졌을 때, 이를 오름차순으로 정렬하는 프로그램을 작성하시오.

```python
N = int(input())
arr = []
for i in range(N):
    arr.append(int(input()))
    
arr.sort()

for i in arr:
    print(i)
```

<img width="734" alt="image" src="https://user-images.githubusercontent.com/46602874/204507263-9b6f2ca7-0a56-48fa-a328-0a5b63e6e7c0.png">

이렇게 쉬운 문제인데,,,  
계속 메모리 초과 에러가 난다...  

검색을 해보니 sort에서 문제였다고 한다.  

```python
import sys

N = int(sys.stdin.readline())
arr = [0] * 10001

for i in range(N):
    tmp = int(sys.stdin.readline())
    arr[tmp] += 1

for i in range(10001):
    if arr[i] != 0:
        tmp = arr[i]
        for j in range(tmp):
            print(i)
```

그래서 대략 힌트를 보고 풀었는데  
이럴수가 DP 문제가 브론즈1이라니,,  
dp 기본기를 다지는 느낌이었다,,
