# 제로

- 링크: https://www.acmicpc.net/problem/10773
- 난이도: Silver IV

```
K = int(input())
arr = []
for i in range(K):
    tmp = int(input())
    if tmp == 0:
        arr.pop(-1)
    else:
        arr.append(tmp)
print(sum(arr))
```

힐링 문제였다~~  
이제 실버의 끝이 보여간다!
