# 직각삼각형

- 링크: https://www.acmicpc.net/problem/4153

'''
while True:
    arr = list(map(int, input().split()))
    _max = max(arr)
    if _max == 0:
        break
    arr.remove(_max) 
    if _max ** 2 == arr[0]**2+arr[1]**2:
        print("right")
    else:
        print("wrong")
'''

오 정말 힐링이다.  
이왕 시작한 거 그래도 클래스2는 빠르게 끝내버려야겠다ㅠㅠ
