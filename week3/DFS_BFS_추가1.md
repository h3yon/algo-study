# N과 M (1)

- 링크: https://www.acmicpc.net/problem/15649
- 정답비율: 	61.695%

## 문제
자연수 N과 M이 주어졌을 때, 아래 조건을 만족하는 길이가 M인 수열을 모두 구하는 프로그램을 작성하시오.
- 1부터 N까지 자연수 중에서 중복 없이 M개를 고른 수열

## 입력
첫째 줄에 자연수 N과 M이 주어진다. (1 ≤ M ≤ N ≤ 8)

## 출력
한 줄에 하나씩 문제의 조건을 만족하는 수열을 출력한다. 중복되는 수열을 여러 번 출력하면 안되며, 각 수열은 공백으로 구분해서 출력해야 한다.

수열은 사전 순으로 증가하는 순서로 출력해야 한다.

## 예제 입력 1 
3 1

## 예제 출력 1 
```
1
2
3
```

## 풀어보기, 회고

```python
from itertools import permutations

n,m = map(int, input().split())
arr = [i for i in range(1, n+1)]

answer = list(permutations(arr, m))
for i in answer:
    for j in i:
        print(j, end=' ', flush=True)
    print()
```

간단하게 이렇게 풀면 되는 거 아닌가? 했는데,  
백트래킹 문제임을 이제 알았다.  

```python
n, m = map(int, input().split())
tmp = []
chk = [False] * (n+1)

def recur(num):
    if num == m:
        print(' '.join(map(str, tmp)))
        return
    
    for i in range(1, n+1):
        if chk[i] == False:
            chk[i] = True
            tmp.append(i)
            recur(num+1)
            chk[i] = False
            tmp.pop()

recur(0)
```

확실히 리트코드 문제 풀면서 느낀 부분은 내가 백트래킹에 약하다는 점이었다,,  
일단 문제를 보면 내가 갔는지에 대한 건 chk에 담는다.  
recur을 돌면서 갯수가 m이면 출력하고 리턴한다.  
m개가 아니면 for문을 돌면서 방문하지 않은 수에 대하여 방문여부를 갱신하고,  
tmp 배열에 그 수를 넣는다.  
그 다음 숫자를 작업해야하니까 recur을 돈다.  
작업을 끝내고 돌아오면 이제 tmp에서 안 해도 되니까 tmp에서 수를 제거해준다.  
더 연습해보면 좋을 것 같다.  
