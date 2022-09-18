# 977. Squares of a Sorted Array

링크: https://leetcode.com/problems/squares-of-a-sorted-array/

Given an integer array nums sorted in non-decreasing order, return an array of the squares of each number sorted in non-decreasing order.  
  
Example 1:

```
Input: nums = [-4,-1,0,3,10]
Output: [0,1,9,16,100]
Explanation: After squaring, the array becomes [16,1,0,9,100].
After sorting, it becomes [0,1,9,16,100].
```

Example 2:

```
Input: nums = [-7,-3,2,3,11]
Output: [4,9,9,49,121]
```

Constraints:

```
1 <= nums.length <= 104
-104 <= nums[i] <= 104
nums is sorted in non-decreasing order.
```

## 풀어보기

```
class Solution:
    def sortedSquares(self, nums: List[int]) -> List[int]:
        abs_nums = list(map(abs, nums))
        squared_nums = sorted(list(map(lambda x: x**2, abs_nums)))
        return squared_nums
```

## 회고

오 오늘 쉬운 문제였지만 그래도 자바의 스트림처럼 사용해본 느낌으로 재밌었다~   
풀이시간: 5분 
