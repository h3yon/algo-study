# 덩치

- 링크: https://www.acmicpc.net/problem/7568
- 난이도: Silver V

```python
num = int(input())
people = []

for _ in range(num):
    w, h = map(int, input().split())
    people.append((w,h))
    
for i in people:
    cnt = 1
    for j in people:
        if i[0] < j[0] and i[1] < j[1]:
                cnt += 1
    print(cnt)
```

enumerate로 하면 되지 않나까지 생각하고   
이중for문을 안 돌리려고 고군분투했다...  
근데 이중 for문 문제였다ㅜㅜ  
다음엔 좀 단순하게 생각하고 다시 풀어봐야겠다.
