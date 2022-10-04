# N과 M (2)

- 문제링크: https://www.acmicpc.net/problem/15650
- 정답비율: 74.194%

## 문제

자연수 N과 M이 주어졌을 때, 아래 조건을 만족하는 길이가 M인 수열을 모두 구하는 프로그램을 작성하시오.
- 1부터 N까지 자연수 중에서 중복 없이 M개를 고른 수열
- 고른 수열은 오름차순이어야 한다.

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

## 풀어보기

```python
n,m = map(int, input().split())
tmp = []

def recur(start):
    if len(tmp) == m:
        print(' '.join(map(str, tmp)))
        return
    
    for i in range(start, n+1):
        if i not in tmp:
            tmp.append(i)
            recur(i+1)
            tmp.pop()

recur(1)
```

원래는 itertools의 combinations을 사용했을 것 같은데,  
백트래킹에 좀 익숙해지고자 N과M(1)문제를 바탕으로 풀었다.  
이번에 좀 다른 건, 들어오는 수보다 커야돼서 recur(start) 로 했다.  
잘 풀려서 다행이다ㅎㅎ
