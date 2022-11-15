# 부녀회장이 될테야

- 링크: https://www.acmicpc.net/problem/2775

'''

T = int(input())

for _ in range(T):  
    floor = int(input())  
    num = int(input())  # 호
    f0 = [x for x in range(1, num+1)]
    for k in range(floor):
        for i in range(1, num):
            f0[i] += f0[i-1]
    print(f0[-1])

'''

# 회고

수학적으로 다른 방법은 없나 했는데.  
그래도 푸니까 좋다~~
