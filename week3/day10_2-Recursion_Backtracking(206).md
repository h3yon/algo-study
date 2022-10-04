# 206. Reverse Linked List

- 문제링크: https://leetcode.com/problems/reverse-linked-list/?envType=study-plan&id=algorithm-i
- 난이도: Easy

Given the head of a singly linked list, reverse the list, and return the reversed list.


Example 1:

<img width="399" alt="image" src="https://user-images.githubusercontent.com/46602874/193883096-24de6a30-bfbb-48a7-8fe1-1417f7cdb877.png">

```
Input: head = [1,2,3,4,5]
Output: [5,4,3,2,1]
```

Example 2:

```
Input: head = [1,2]
Output: [2,1]
```

Example 3:

```
Input: head = []
Output: []
```
 

## Constraints:

- The number of nodes in the list is the range [0, 5000].
- -5000 <= Node.val <= 5000

## 풀어보기

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def reverseList(self, head: Optional[ListNode]) -> Optional[ListNode]:
        prev = None
        while head:
            _next = head.next;
            head.next = prev;
            prev = head;
            head = _next;
        
        return prev;
```

확실히 리스트노드가 아직 익숙하지 않은 듯 하다.  
이 부분은 그림을 더 그리고 더 이해할 수 있을 것으로 보인다.  
다음에 한번 더 시도해봐야겠다!
 
