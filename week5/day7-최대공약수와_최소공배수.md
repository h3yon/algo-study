# 최대공약수와 최소공배수

- 문제링크: https://www.acmicpc.net/problem/2609
- 난이도: 🥈실버 5티어

두 개의 자연수를 입력받아 최대 공약수와 최소 공배수를 출력하는 프로그램을 작성하시오.

```python
from math import gcd

a,b = map(int, input().split())
_max = gcd(a,b)
print(_max)
print((a*b)//_max)
```

위처럼 푸는 문제가 아닌 것으로 생각이 된다.   
호제법이란 말은 두 수가 서로 상대방 수를 나누어서 결국 원하는 수를 얻는 알고리즘이라고 한다.  
라이브러리를 사용하지 않고 어떻게 최대 공약수를 구할 수 있을까?  

```python
def gcd(a, b):
    while b > 0:
        a, b = b, a % b
    return a
```

이렇게 하면 된다고 한다.
싱기!
