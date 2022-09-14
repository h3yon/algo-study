# 704. Binary Search

- 문제 링크: https://leetcode.com/problems/binary-search/  

Given an array of integers nums which is sorted in ascending order, and an integer target,  
write a function to search target in nums. If target exists, then return its index. Otherwise, return -1.  
You must write an algorithm with O(log n) runtime complexity.  
  
Example 1:
```
Input: nums = [-1,0,3,5,9,12], target = 9
Output: 4
Explanation: 9 exists in nums and its index is 4
```

Example 2:

```
Input: nums = [-1,0,3,5,9,12], target = 2
Output: -1
Explanation: 2 does not exist in nums so return -1
```
 
Constraints:

- 1 <= nums.length <= 10^4
- -10^4 < nums[i], target < 10^4
- All the integers in nums are unique.
- nums is sorted in ascending order.

## 풀어보기

```python
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        try:
            return nums.index(target)
        except:
            return -1
```

하지만 이렇게 풀면  
면접에서 다시 풀라고 한다.  

```python
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        start = 0
        end = len(nums)

        while start < end:
            mid = ((end-start) // 2) + start
            if nums[mid] == target:
                return mid
            elif nums[mid] > target:
                end = mid
            elif nums[mid] < target:
                start = mid+1
        return -1
```

## 회고

처음부터 중요한 문제가 나와서 조금 놀랐다.  
면접에서도 풀라고 하는만큼 중요한 문제라 오늘 풀어서 기분이 좋았다!
