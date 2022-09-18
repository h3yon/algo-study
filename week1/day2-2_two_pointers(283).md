# 283. Move Zeroes

- 난이도: Easy
- 링크: https://leetcode.com/problems/move-zeroes/

Given an integer array nums, move all 0's to the end of it while maintaining the relative order of the non-zero elements.  

Note that you must do this in-place without making a copy of the array.  

 

Example 1:

```
Input: nums = [0,1,0,3,12]
Output: [1,3,12,0,0]
```

Example 2:

```
Input: nums = [0]
Output: [0]
```
 
Constraints:

- 1 <= nums.length <= 104
- -231 <= nums[i] <= 231 - 1

## 풀어보기

```
class Solution:
    def moveZeroes(self, nums: List[int]) -> None:
        """
        Do not return anything, modify nums in-place instead.
        """
        left = [i for i in nums if i != 0]
        right = [i for i in nums if i == 0]
        
        nums[:] = left + right
```

## 회고

쉬운 문제였지만 위에 코드를 봤을 때 시간복잡도 면에 있어서 불리하지 않나 싶었다.  
'faster than 95.64% of Python3 online submissions for Move Zeroes.' 문구를 보고  
다행이다 싶긴 했는데 흠..  
확실히 다른 코드보다는 더 빨라서 일단은 만족한다!
