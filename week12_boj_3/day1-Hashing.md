# Hashing

- 링크: https://www.acmicpc.net/problem/15829
- 난이도: Bronze II

와 처음에 이걸 어떻게 풀지 했다.  
고등학생 때 배웠던 공식들을 계속 생각했는데,  
결국 궁금해서 답을 보았다.  
이렇게 풀 수 있구나를 생각했고 이번 문제의 핵심은  
ord(문자)-96이었다고 생각한다~!  

```python
l = int(input())
tmp = input()
res = 0

for i in range(l):
    res += ((ord(tmp[i])-96) * (31 ** i))
print(res % 1234567891)
```
