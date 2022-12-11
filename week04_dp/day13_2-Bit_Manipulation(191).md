# 191. Number of 1 Bits

- 링크: https://leetcode.com/problems/number-of-1-bits/
- 난이도: Easy

Write a function that takes an unsigned integer and returns the number of '1' bits it has (also known as the Hamming weight).  

Note:

Note that in some languages, such as Java, there is no unsigned integer type.  
In this case, the input will be given as a signed integer type.  
It should not affect your implementation, as the integer's internal binary representation is the same, whether it is signed or unsigned.  
In Java, the compiler represents the signed integers using 2's complement notation.  
Therefore, in Example 3, the input represents the signed integer. -3.  
 

Example 1:

```
Input: n = 00000000000000000000000000001011
Output: 3
Explanation: The input binary string 00000000000000000000000000001011 has a total of three '1' bits.
```

Example 2:

```
Input: n = 00000000000000000000000010000000
Output: 1
Explanation: The input binary string 00000000000000000000000010000000 has a total of one '1' bit.
```

Example 3:

```
Input: n = 11111111111111111111111111111101
Output: 31
Explanation: The input binary string 11111111111111111111111111111101 has a total of thirty one '1' bits.
```

Constraints:

- The input must be a binary string of length 32.

# 풀어보기

```python
from collections import Counter

class Solution:
    def hammingWeight(self, n: int) -> int:
        return Counter(bin(n))['1']
```

binary로 바꾸고 1이 나오는 부분을 찾으면 되는 문제이다.  
비트를 사용하여 풀 수 있는 문제임은 알고 있지만 손이 잘 안 간다ㅜ  
빠르게 다른 주제로 넘어가서 더 공부를 해야겠다.
