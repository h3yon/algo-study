# 나무 자르기

- 링크: https://www.acmicpc.net/problem/2805


'''

N, M = map(int, input().split())
tree = list(map(int, input().split()))
start, end = 1, max(tree)

while start <= end:
    mid = (start + end) // 2
    
    log = 0
    for i in tree:
        if i >= mid:
            log += i - mid
    
    if log >= M:
        start = mid + 1
    else:
        end = mid - 1
print(end)
'''

시간초과로 처음에 ??? 물음표가 가득했지만.  
이럴 때 이분탐색을 사용해야함을 알 수 있었다!
