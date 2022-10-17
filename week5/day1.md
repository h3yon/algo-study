# 약수 구하기

- 링크: https://www.acmicpc.net/problem/2501
- 난이도: 🥉 브론즈 3티어

어떤 자연수 p와 q가 있을 때, 만일 p를 q로 나누었을 때 나머지가 0이면 q는 p의 약수이다.  

6을 예로 들면  

```
6 ÷ 1 = 6 … 0
6 ÷ 2 = 3 … 0
6 ÷ 3 = 2 … 0
6 ÷ 4 = 1 … 2
6 ÷ 5 = 1 … 1
6 ÷ 6 = 1 … 0
```

그래서 6의 약수는 1, 2, 3, 6, 총 네 개이다.  

두 개의 자연수 N과 K가 주어졌을 때, N의 약수들 중 K번째로 작은 수를 출력하는 프로그램을 작성하시오.  

# 문제 풀기

```python
p,q = map(int, input().split())
answer = []
for i in range(1, p+1):
    if p % i == 0:
        answer.append(i)
if len(answer) < q:
    print(0)
else:
    print(answer[q-1])
```

# 회고

확실히 쉬운 문제였다.  
힐링됐다~
