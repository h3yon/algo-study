# 단어 정렬

- 문제링크: https://www.acmicpc.net/problem/1181
- 난이도: Silver V

알파벳 소문자로 이루어진 N개의 단어가 들어오면 아래와 같은 조건에 따라 정렬하는 프로그램을 작성하시오.  

- 길이가 짧은 것부터
- 길이가 같으면 사전 순으로

## 예제

```
13
but
i
wont
hesitate
no
more
no
more
it
cannot
wait
im
yours
```

## 출력

```
i
im
it
no
but
more
wait
wont
yours
cannot
hesitate
```

## 풀어보기

정렬은 진짜 힐링타임인 것 같다.  
다 풀어서 좋다~

```python
n = int(input())
arr = []

for i in range(n):
    arr.append(input())

_arr = list(set(arr))
_arr[:] = sorted(_arr, key = lambda x:  [len(x), x])

for i in _arr:
    print(i)
```
