# 344. 557. Reverse Words in a String III

- 난이도: Easy
- 링크: https://leetcode.com/problems/reverse-words-in-a-string-iii/

Given a string s, reverse the order of characters in each word within a sentence while still  
preserving whitespace and initial word order.

 

Example 1:

```
Input: s = "Let's take LeetCode contest"
Output: "s'teL ekat edoCteeL tsetnoc"
```

Example 2:

```
Input: s = "God Ding"
Output: "doG gniD"
```
 

Constraints:

- 1 <= s.length <= 5 * 104
- s contains printable ASCII characters.
- s does not contain any leading or trailing spaces.
- There is at least one word in s.
- All the words in s are separated by a single space.

# 풀어보기 

```python
class Solution(object):
    def reverseWords(self, s):
        """
        :type s: str
        :rtype: str
        """
        answer = []
        for i in s.split():
            answer.append(i[::-1])
        return ' '.join(answer)
```

# 회고

파이썬으로 거꾸로 된 문자열은 처음 해봤다!  
경험으로 좋았다고 생각했다~
