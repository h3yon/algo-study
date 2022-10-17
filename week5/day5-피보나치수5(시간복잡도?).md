# 피보나치 수 5

- 링크: https://www.acmicpc.net/problem/10870
- 난이도: 🥉 브론즈 2티어

피보나치 수는 0과 1로 시작한다.  
0번째 피보나치 수는 0이고, 1번째 피보나치 수는 1이다.  
그 다음 2번째 부터는 바로 앞 두 피보나치 수의 합이 된다.  

이를 식으로 써보면 Fn = Fn-1 + Fn-2 (n ≥ 2)가 된다.  

n=17일때 까지 피보나치 수를 써보면 다음과 같다.  

0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, 233, 377, 610, 987, 1597  

n이 주어졌을 때, n번째 피보나치 수를 구하는 프로그램을 작성하시오.  

# 풀어보기

```python
n = int(input())

fibo = [0] * (n+1)
fibo[0], fibo[1] = 0, 1
for i in range(2, n+1):
    fibo[i] = fibo[i-1] + fibo[i-2]

print(fibo[n])
```

dp가 생각이 나서 위처럼 풀었는데,  
흠,, 런타임에러가 난다..  

```python
n = int(input())

def fibo(num):
    if num == 0:
        return 0
    elif num == 1:
        return 1
    else:
        return fibo(num-1) + fibo(num-2)

print(fibo(n))
```

전형적인 피보나치로 풀면 빠르게 나온다.  
흠.. 시간복잡도가 어떻게 되는지 한번 찾아보는 게 좋겠다.
