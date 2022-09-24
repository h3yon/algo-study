# 567. Permutation in String

- 링크: https://leetcode.com/problems/permutation-in-string/
- 난이도: Medium
- 풀이시간: 10분. + time limit 후 30분

Given two strings s1 and s2, return true if s2 contains a permutation of s1, or false otherwise.  
In other words, return true if one of s1's permutations is the substring of s2.

 
Example 1:

```
Input: s1 = "ab", s2 = "eidbaooo"
Output: true
Explanation: s2 contains one permutation of s1 ("ba").
```

Example 2:

```
Input: s1 = "ab", s2 = "eidboaoo"
Output: false
```

Constraints:

- 1 <= s1.length, s2.length <= 104
- s1 and s2 consist of lowercase English letters.

# 풀어보기 & 회고

```python
from itertools import permutations

class Solution:
    def checkInclusion(self, s1: str, s2: str) -> bool:
        if len(s1) > len(s2):
            return False
        arr = list(permutations(s1, len(s1)))
        
        for a in arr:
            tmp = ''.join(a)
            if tmp in s2:
                return True
        return False
        
```

계속 time limit exceeded 문제가 났다.  
확인해보니 permutations 라이브러리를 사용하면 해당 에러가 나타난다.

```python
class Solution:
    def checkInclusion(self, s1: str, s2: str) -> bool:
        for i in range(len(s2)-len(s1)+1):
            if Counter(s1) == Counter(s2[i:i+len(s1)]):
                return True
```

대체 어떻게 해야할까 하고 해설을 봤는데,  
아 이렇게 풀 수 있구나를 느꼈다. 이럴수가...  
진짜 분발해야겠다ㅜ

- 해설 링크: https://jyj98020.tistory.com/149
