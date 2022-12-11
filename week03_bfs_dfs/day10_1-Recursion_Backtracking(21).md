# 21. Merge Two Sorted Lists

- 링크: https://leetcode.com/problems/merge-two-sorted-lists/?envType=study-plan&id=algorithm-i
- 난이도: Easy

You are given the heads of two sorted linked lists list1 and list2.  

Merge the two lists in a one sorted list.  
The list should be made by splicing together the nodes of the first two lists.  

Return the head of the merged linked list.  

 

Example 1:

<img width="484" alt="image" src="https://user-images.githubusercontent.com/46602874/193873567-e360f30c-933d-4536-ab0f-215b3f43a1c9.png">

```
Input: list1 = [1,2,4], list2 = [1,3,4]
Output: [1,1,2,3,4,4]
```

Example 2:

```
Input: list1 = [], list2 = []
Output: []
```

Example 3:

```
Input: list1 = [], list2 = [0]
Output: [0]
```
 
### Constraints:

- The number of nodes in both lists is in the range [0, 50].
- -100 <= Node.val <= 100
- Both list1 and list2 are sorted in non-decreasing order.

## 풀어보기 

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def mergeTwoLists(self, list1: Optional[ListNode], list2: Optional[ListNode]) -> Optional[ListNode]:
        cur = dummy = ListNode()
        while list1 and list2:
            if list1.val < list2.val:
                cur.next = list1
                list1, cur = list1.next, list1
            else: #list1.val >= list2.val
                cur.next = list2
                list2, cur = list2.next, list2
        
        if list1 or list2:
            cur.next = list1 if list1 else list2
        
        return dummy.next
```

오! 어렵다ㅎㅎ  
작은쪽을 cur에다가 배정해주었고,  
어느 한쪽의 리스트만 남았을 때에는 cur 다음에 배정해주었다.  
더미에 다 담겨져 있을 것이기 때문에 dummy의 next를 리턴해주면 되는 것을 알 수 있다.
