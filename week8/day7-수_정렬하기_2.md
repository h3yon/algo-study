# 수 정렬하기 2

- 링크: https://www.acmicpc.net/problem/2751
- 난이도: Silver V

N개의 수가 주어졌을 때, 이를 오름차순으로 정렬하는 프로그램을 작성하시오.

## 입력
첫째 줄에 수의 개수 N(1 ≤ N ≤ 1,000,000)이 주어진다. 둘째 줄부터 N개의 줄에는 수가 주어진다.  
이 수는 절댓값이 1,000,000보다 작거나 같은 정수이다. 수는 중복되지 않는다.  

### 예제 입력 1 
```
5
5
4
3
2
1
```

## 출력

첫째 줄부터 N개의 줄에 오름차순으로 정렬한 결과를 한 줄에 하나씩 출력한다.

### 예제 출력 1 

```
1
2
3
4
5
```

## 풀어보기

```python
n = int(input())
arr = set()

for i in range(n):
    arr.add(int(input()))

for i in list(sorted(arr)):
    print(i)
```

아니 이렇게 쉬운 문제라니! 하고 있었는데,  
이게 웬걸 시간초과가ㅎㅎ  

```python
import sys

n = int(input())
arr = set()

for i in range(n):
    arr.add(int(sys.stdin.readline()))

for i in list(sorted(arr)):
    print(i)
```

당황스럽게도 sys로 하니까 시간초과가 나지 않는다 흠,,  
일단 그런 걸로,,!
