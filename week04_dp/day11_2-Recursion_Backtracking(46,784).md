# 46. Permutations

- 문제: https://leetcode.com/problems/permutations/
- 난이도: Medium

```python
from itertools import permutations
class Solution:
    def permute(self, nums: List[int]) -> List[List[int]]:
        return list(permutations(nums, len(nums)))
```

문제를 보았을 때 당연히 이걸 의도하지 않은 문제라는 건 알지만,  
항상 짧은 코드와 라이브러리를 신뢰하는 나로서는 다시 풀지에 대해 고민되는 부분이었다..  
그래서 해당 문제를 안 푼 걸로 하고 다음 문제로 넘어갔다.

# 784. Letter Case Permutation

- 문제: https://leetcode.com/problems/letter-case-permutation/
- 난이도: Medium

Example 1:

```
Input: s = "a1b2"
Output: ["a1b2","a1B2","A1b2","A1B2"]
```

Example 2:

```
Input: s = "3z4"
Output: ["3z4","3Z4"]
```

## 풀어보기

```python
class Solution:
    def letterCasePermutation(self, s: str) -> List[str]:
        def backtrack(sub="", i=0):
            if len(sub) == len(s):
                res.append(sub)
            else:
                if s[i].isalpha():
                    backtrack(sub + s[i].swapcase(), i + 1)
                backtrack(sub + s[i], i + 1)
                
        res = []
        backtrack()
        return res
```

이 문제는 예제만 보면 알 수 있는 문제이다.  
이걸 어떻게 하지 했는데 백트래킹으로 풀면 됨을 알 수 있다.  
alpha일 경우 대문자와, 소문자를 각각 해서 문자열을 만들어주면 된다.  
넘 재밌었다. 담에도 풀어도 좋을 것 같다~

