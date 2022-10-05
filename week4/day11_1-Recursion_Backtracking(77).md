# 77. Combinations

- 문제링크: https://leetcode.com/problems/combinations/
- 난이도: Medium

Given two integers n and k, return all possible combinations of k numbers chosen from the range [1, n].  

You may return the answer in any order.  

## 풀어보기

```python
from itertools import combinations

class Solution:
    def combine(self, n: int, k: int) -> List[List[int]]:
        return list(combinations(range(1, n+1), k))
```

이게 핵심이 아닐 것으로 보인다.  
내 생각에 내일 다시 풀어야 할 것 같다.  
어떻게 Recursion, Backtracking을 사용해서 풀 수 있을지 생각해보자!
