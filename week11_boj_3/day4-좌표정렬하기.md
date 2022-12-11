# 좌표 정렬하기

- 링크: https://www.acmicpc.net/problem/11650
- 난이도: Silver V

2차원 평면 위의 점 N개가 주어진다.  
좌표를 x좌표가 증가하는 순으로, x좌표가 같으면 y좌표가 증가하는 순서로 정렬한 다음 출력하는 프로그램을 작성하시오.

## 예시

- 입력

    ```
    5
    3 4
    1 1
    1 -1
    2 2
    3 3
    ```

- 출력

    ```
    1 -1
    1 1
    2 2
    3 3
    3 4
    ```

## 풀어보기

```python
n = int(input())
arr = []

for i in range(n):
    a,b = map(int, input().split())
    arr.append((a,b))

arr[:] = sorted(arr, key=lambda x: [x[0], x[1]])

for a,b in arr:
    print(a,b)
```

그냥 작은것부터 출력하면 성공한다!
