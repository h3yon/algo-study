# Z

- 링크: https://www.acmicpc.net/problem/1074
- 난이도: Silver I

## 문제
한수는 크기가 2N × 2N인 2차원 배열을 Z모양으로 탐색하려고 한다.  
예를 들어, 2×2배열을 왼쪽 위칸, 오른쪽 위칸, 왼쪽 아래칸, 오른쪽 아래칸 순서대로 방문하면 Z모양이다.  

![image](https://user-images.githubusercontent.com/46602874/206205422-ef856de0-6f90-4be9-9b9f-6e16019a0b26.png)

N > 1인 경우, 배열을 크기가 2N-1 × 2N-1로 4등분 한 후에 재귀적으로 순서대로 방문한다.  
다음 예는 22 × 22 크기의 배열을 방문한 순서이다.  

![image](https://user-images.githubusercontent.com/46602874/206205454-cf03019a-511d-42f3-835d-190667603d7a.png)

N이 주어졌을 때, r행 c열을 몇 번째로 방문하는지 출력하는 프로그램을 작성하시오.  
다음은 N=3일 때의 예이다.  

![image](https://user-images.githubusercontent.com/46602874/206205492-8fc414a4-20d3-4486-a4ce-c964e7b5f49c.png)

## 입력

첫째 줄에 정수 N, r, c가 주어진다.

### 예제 입력 1 
2 3 1

### 예제 입력 2 
3 7 7

## 출력

r행 c열을 몇 번째로 방문했는지 출력한다.

### 예제 출력 1 

11

### 예제 출력 2 
63

## 풀어보기

```python
N, r, c = map(int, input().split())

ans = 0

while N != 0:

	N -= 1

	# 1사분면
	if r < 2 ** N and c < 2 ** N:
		ans += ( 2 ** N ) * ( 2 ** N ) * 0

	# 2사분면
	elif r < 2 ** N and c >= 2 ** N: 
		ans += ( 2 ** N ) * ( 2 ** N ) * 1
		c -= ( 2 ** N )
        
	# 3사분면    
	elif r >= 2 ** N and c < 2 ** N: 
		ans += ( 2 ** N ) * ( 2 ** N ) * 2
		r -= ( 2 ** N )
        
	# 4사분면    
	else:
		ans += ( 2 ** N ) * ( 2 ** N ) * 3
		r -= ( 2 ** N )
		c -= ( 2 ** N )
    
print(ans)
```

와 이걸 이렇게 풀다니,,,  
이런 문제가 나에게 진짜 어렵게 다가온다.  
다시 한번 더 풀면 좋을 것 같다.
