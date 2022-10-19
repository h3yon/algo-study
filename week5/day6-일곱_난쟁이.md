# 일곱 난쟁이

- 링크: https://www.acmicpc.net/problem/2309
- 난이도: 🥉 브론즈 2티어

왕비를 피해 일곱 난쟁이들과 함께 평화롭게 생활하고 있던 백설공주에게 위기가 찾아왔다.  
일과를 마치고 돌아온 난쟁이가 일곱 명이 아닌 아홉 명이었던 것이다.  

아홉 명의 난쟁이는 모두 자신이 "백설 공주와 일곱 난쟁이"의 주인공이라고 주장했다.   
뛰어난 수학적 직관력을 가지고 있던 백설공주는, 다행스럽게도 일곱 난쟁이의 키의 합이 100이 됨을 기억해 냈다.  

아홉 난쟁이의 키가 주어졌을 때, 백설공주를 도와 일곱 난쟁이를 찾는 프로그램을 작성하시오.  

# 풀어보기

```python
from itertools import combinations

dwarf = [int(input()) for _ in range(9)]
seven = list(combinations(dwarf, 7))

for i in seven:
    if sum(i) == 100:
        ans = list(i)
        break

ans = sorted(ans)
for _ans in ans:
    print(_ans)
```

DFS문제인 줄 알았는데, 문제를 계속 보니 9명 중 7명일 경우 100이 되는 걸 찾는 문제니까,  
그냥 조합을 이용하면 되는구나를 깨달았다ㅎㅎ
