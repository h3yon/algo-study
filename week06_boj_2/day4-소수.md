# 소수

- 링크: https://www.acmicpc.net/problem/2581
- 난이도: 🥈실버 4티어

자연수 M과 N이 주어질 때 M이상 N이하의 자연수 중 소수인 것을 모두 골라 이들 소수의 합과 최솟값을 찾는 프로그램을 작성하시오.  

예를 들어 M=60, N=100인 경우 60이상 100이하의 자연수 중 소수는 61, 67, 71, 73, 79, 83, 89, 97 총 8개가 있으므로,  
이들 소수의 합은 620이고, 최솟값은 61이 된다.

## 입력

입력의 첫째 줄에 M이, 둘째 줄에 N이 주어진다.  
M과 N은 10,000이하의 자연수이며, M은 N보다 작거나 같다.

```
60
100
```

##  출력

M이상 N이하의 자연수 중 소수인 것을 모두 찾아 첫째 줄에 그 합을, 둘째 줄에 그 중 최솟값을 출력한다.   
단, M이상 N이하의 자연수 중 소수가 없을 경우는 첫째 줄에 -1을 출력한다.


```
620
61
```

## 풀어보기

```python
import math

# function
def is_prime(num):
    if num < 2:
        return False
    for i in range(2, num):
        if num % i == 0:
            return False
    return True

# main
start = int(input())
end = int(input())

arr = []
for num in range(start, end+1):
    if is_prime(num) == True:
        arr.append(num)

if len(arr) == 0:
    print(-1)
else:
    print(sum(arr))
    print(min(arr))
```

오늘은 소수를 많이 푸는 것 같다!
math.sqrt를 쓰려고 했는데, 계속 틀려서 이것저것 다 고쳐보았다.  
알고보니까 소수가 없을 경우 그냥 arr.append(-1)을 해주었었는데, 그럼 sum(arr), min(arr)로 -1이 2번 출력되니까  
계속 틀린 부분이었다ㅎㅎ  
이 부분에 시간 계속 쓴 부분은 아쉬웠지만,  
차근차근 잘 생각해보아야겠다고 느꼈다.
