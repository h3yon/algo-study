# 19. Remove Nth Node From End of List

- 난이도: Medium
- 링크: https://leetcode.com/problems/remove-nth-node-from-end-of-list/

Given the head of a linked list, remove the nth node from the end of the list and return its head.


Example 1:

```
Input: head = [1,2,3,4,5], n = 2
Output: [1,2,3,5]
```

Example 2:

```
Input: head = [1], n = 1
Output: []
```

Example 3:

```
Input: head = [1,2], n = 1
Output: [1]
```

Constraints:

- The number of nodes in the list is sz.
- 1 <= sz <= 30
- 0 <= Node.val <= 100
- 1 <= n <= sz

## 풀어보기

```python
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution(object):
    def removeNthFromEnd(self, head, n):
        """
        :type head: ListNode
        :type n: int
        :rtype: ListNode
        """
        start = ListNode(next = head)
        slow = start
        fast = start
        
        # n까지 간다
        for i in range(n):
            fast = fast.next
        
        
        while fast.next != None:
            slow = slow.next
            fast = fast.next
            
        slow.next = slow.next.next
        return start.next
        
```

## 회고

와 이걸 어려워할 줄은 몰랐다.  
공부를 더 하고 다시 풀어봐야겠다
