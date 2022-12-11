# 231. Power of Two

- 링크: https://leetcode.com/problems/power-of-two/
- 난이도: Easy

Given an integer n, return true if it is a power of two. Otherwise, return false.  

An integer n is a power of two, if there exists an integer x such that n == 2x.  

 

Example 1:

```
Input: n = 1
Output: true
Explanation: 20 = 1
```

Example 2:

```
Input: n = 16
Output: true
Explanation: 24 = 16
```

Example 3:

```
Input: n = 3
Output: false
```

## 풀어보기

```Python
class Solution:
    def isPowerOfTwo(self, n: int) -> bool:
        while n > 1:
            if n % 2 == 0:
                n //= 2
            else:
                return False
        if n < 1:
            return False
        return True
```
 
난 이렇게 풀었었다.  
그런데 다른 사람들 풀이를 보니 충격적이었다.

```python
class Solution:
    def isPowerOfTwo(self, n: int) -> bool:
        return n>0 and n&(n-1)==0
```

아래를 참고해서 n&(n-1) 해서 0으로 푸셨다는 걸 보고 충격 받았다,,  
이걸 알아낸다는 게 대단한 것 같다.

```
     <----- binary ---->
 n      n    n-1   n&(n-1)
--   ----   ----   -------
 0   0000   0111    0000 *
 1   0001   0000    0000 *
 2   0010   0001    0000 *
 3   0011   0010    0010
 4   0100   0011    0000 *
 5   0101   0100    0100
 6   0110   0101    0100
 7   0111   0110    0110
 8   1000   0111    0000 *
 9   1001   1000    1000
10   1010   1001    1000
11   1011   1010    1010
12   1100   1011    1000
13   1101   1100    1100
14   1110   1101    1100
15   1111   1110    1110
```

