# 189. Rotate Array

- 난이도: Medium
- 링크: https://leetcode.com/problems/rotate-array/

Given an array, rotate the array to the right by k steps, where k is non-negative.


Example 1:
```
Input: nums = [1,2,3,4,5,6,7], k = 3
Output: [5,6,7,1,2,3,4]
Explanation:
rotate 1 steps to the right: [7,1,2,3,4,5,6]
rotate 2 steps to the right: [6,7,1,2,3,4,5]
rotate 3 steps to the right: [5,6,7,1,2,3,4]
```

Example 2:
```
Input: nums = [-1,-100,3,99], k = 2
Output: [3,99,-1,-100]
Explanation: 
rotate 1 steps to the right: [99,-1,-100,3]
rotate 2 steps to the right: [3,99,-1,-100]
```

Constraints:
- 1 <= nums.length <= 105
- -231 <= nums[i] <= 231 - 1
- 0 <= k <= 105
 
 ## 풀어보기
 
 ```
 from collections import deque

class Solution:
    def rotate(self, nums: List[int], k: int) -> None:
        """
        Do not return anything, modify nums in-place instead.
        """
        queue = deque(nums)
        queue.rotate(k)
        nums[:] = list(queue)
 ```
 
많이 풀어봤던 문제여서 일단 간단하게 풀어봤는데,  
`nums = list(queue)`로 하면 안 되고 `nums[:]` 로 해야 돌아가는 게 신기했다.  
근데 생각해보면 면접관 입장에서는 저 utils를 사용한 방식을 원하지 않을 수도 있다.  
그래서 아래처럼 다시 풀어봤다.

```
class Solution:
    def rotate(self, nums: List[int], k: int) -> None:
        """
        Do not return anything, modify nums in-place instead.
        """ 
        for i in range(k):
            nums.insert(0, nums.pop(-1))
```

 
 ## 회고
 
 경력직 코테에 아무것도 모르고 지원을 좀 해봤을 때, 많이 봤던 문제이다.  
 이번에 알게 된 부분은 list에는 append를 엄청 써왔는데, `insert(위치, 값)` 을 써도 된다는 생각을 했다.
 
