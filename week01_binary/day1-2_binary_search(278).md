# 278. First Bad Version

- 문제 링크: https://leetcode.com/problems/first-bad-version/

You are a product manager and currently leading a team to develop a new product.  
Unfortunately, the latest version of your product fails the quality check.  
Since each version is developed based on the previous version, all the versions after a bad version are also bad.  

Suppose you have n versions [1, 2, ..., n] and you want to find out the first bad one, which causes all the following ones to be bad.  

You are given an API bool isBadVersion(version) which returns whether version is bad.  
Implement a function to find the first bad version. You should minimize the number of calls to the API.  

 

Example 1:
```
Input: n = 5, bad = 4
Output: 4
Explanation:
call isBadVersion(3) -> false
call isBadVersion(5) -> true
call isBadVersion(4) -> true
Then 4 is the first bad version.
```

Example 2:

```
Input: n = 1, bad = 1
Output: 1
``` 


## 풀어보기 

처음 문제를 보고 이해를 하지 못했다.  
다시 차근차근 계속 읽어보니, isBadVersion이라는 함수는 이미 정의되어 있고 그걸 사용하라고 한다.  
bad 이후에는 다 true고, 그 전까지는 false이다.  
이 isBadVersion의 호출 수를 최소한으로 해야하기 때문에 주제에 맞게 이진탐색이구나를 깨달았다.  
  
이해한 후에는 문제가 쉬웠다.  
1-1때 풀었던 것처럼 풀었다.

```python
class Solution:
    def firstBadVersion(self, n: int) -> int:
        left = 1
        right = n
        while left < right:
            mid = (left + right) // 2
            if isBadVersion(mid) == True:
                right = mid
            else:
                left = mid + 1
        return left
```

## 회고

확실히 1-1 문제가 제일 기초적인 문제였다면,  
이번 문제는 이해하는데 시간이 좀 걸렸다.  
이진탐색에서 이러한 문제가 나올 수 있구나를 느꼈고,  
확실히 프로그래머스와는 다른 느낌의 알고리즘 문제였음을 느꼈다!


