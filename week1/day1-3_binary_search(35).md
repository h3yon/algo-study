# 35. Search Insert Position

문제링크: https://leetcode.com/problems/search-insert-position/  

Given a sorted array of distinct integers and a target value,  
return the index if the target is found. If not, return the index where it would be if it were inserted in order.  

You must write an algorithm with O(log n) runtime complexity.  

 

Example 1:

```
Input: nums = [1,3,5,6], target = 5
Output: 2
```

Example 2:

```
Input: nums = [1,3,5,6], target = 2
Output: 1
```

Example 3:

```
Input: nums = [1,3,5,6], target = 7
Output: 4
```

## 풀어보기

```python
class Solution:
    def searchInsert(self, nums: List[int], target: int) -> int:
        for i in range(len(nums)):
            if nums[i] >= target:
                return i
        return len(nums)
```

## 회고

지금까지 풀었던 이진탐색으로 풀고 싶었다.  
그런데 아무리 생각해도 left, right로 풀 방법으로는 딱히 떠오르지 않았다.  
그래서 고전적으로 for문을 사용했다.  
이 부분은 내가 다른 방법이 있는지 생각해봐야겠다.
