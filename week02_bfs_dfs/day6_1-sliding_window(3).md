# 3. Longest Substring Without Repeating Characters

- 난이도: Medium
- 문제: https://leetcode.com/problems/longest-substring-without-repeating-characters/
- 풀이시간: 40분

Given a string s, find the length of the longest substring without repeating characters.

Example 1:

```
Input: s = "abcabcbb"
Output: 3
Explanation: The answer is "abc", with the length of 3.
```

Example 2:

```
Input: s = "bbbbb"
Output: 1
Explanation: The answer is "b", with the length of 1.
```

Example 3:

```
Input: s = "pwwkew"
Output: 3
Explanation: The answer is "wke", with the length of 3.
Notice that the answer must be a substring, "pwke" is a subsequence and not a substring.
```
 

Constraints:

- 0 <= s.length <= 5 * 104
- s consists of English letters, digits, symbols and spaces.

# 풀어보기

```python
class Solution:
    def lengthOfLongestSubstring(self, s: str) -> int:
        # sets = set()
        record = set(s[0])
        tmp = s[0]
        for i, val in enumerate(s[1:]):
            if len(tmp) == 0 or tmp[-1] != val:
                tmp += val
            else:
                continue
            
            if tmp in record:
                tmp = ''
            record.add(tmp)
        
        lr = list(record)
        for a in lr[1:]:
            for b in lr:
                if a in b:
                    print(a,b)
        
```

흠..어려운 것 같아서 해설을 봤다ㅜ

```python
class Solution:
    def lengthOfLongestSubstring(self, s: str) -> int:
        if s == "":
            return 0
        start = 0
        end = 0
        maxLength = 0
        
        unique_characters = set()
        while end < len(s):
            if s[end] not in unique_characters:
                unique_characters.add(s[end])
                end += 1
                maxLength = max(maxLength, len(unique_characters))
            else:
                unique_characters.remove(s[start])
                start += 1
        return maxLength
```


# 회고

와 40분.. 지금까지 약한 linkedList를 제외하고 풀이시간이 5~10분컷이었어서 오늘은 좀 충격적이었다.  
시간이 지나도 잘 풀지 못하겠어서 해설을 참고했다.  
해설을 보고 또 충격적이었는데, 이렇게 풀 수도 있구나를 알게 됐다.  
분발하는걸로!!

# 해설 링크

https://redquark.org/leetcode/0003-longest-substring-without-repeating-characters/

