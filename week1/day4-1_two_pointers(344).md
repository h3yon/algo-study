# 344. Reverse String

- 난이도: Easy
- 링크: https://leetcode.com/problems/reverse-string/submissions/

Write a function that reverses a string. The input string is given as an array of characters s.

You must do this by modifying the input array in-place with O(1) extra memory.

 

Example 1:

```
Input: s = ["h","e","l","l","o"]
Output: ["o","l","l","e","h"]
```

Example 2:

```
Input: s = ["H","a","n","n","a","h"]
Output: ["h","a","n","n","a","H"]
```
 

Constraints:
- 1 <= s.length <= 105
- s[i] is a printable ascii character.

# 풀어보기 

```python
class Solution:
    def reverseString(self, s: List[str]) -> None:
        return s.reverse()
```

당연히 안 될 줄 알았는데 통과했다!  
근데 이렇게 하면 면접에서 100% 다시 풀라고 할 것 같다.
근데 잘 생각이 안 난답ㅎㅎ

# 회고

그럼 어떻게 풀어야 할까?

```python
class Solution:
    def reverseString(self, s: List[str]) -> None:
        p, q = 0, len(s)-1
        while p < q:
            s[p], s[q] = s[q], s[p]
        p,q = p+1, q-1
        return s
```

아 이렇게 푸는거구나를 느꼈다.  
더 공부를 해야겠다.
