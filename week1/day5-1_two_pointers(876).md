# 876. Middle of the Linked List

- 난이도: easy
- 링크: https://leetcode.com/problems/middle-of-the-linked-list/description/

Given the head of a singly linked list, return the middle node of the linked list.

If there are two middle nodes, return the second middle node.

 

Example 1:

'''
Input: head = [1,2,3,4,5]
Output: [3,4,5]
Explanation: The middle node of the list is node 3.
'''

Example 2:

'''
Input: head = [1,2,3,4,5,6]
Output: [4,5,6]
Explanation: Since the list has two middle nodes with values 3 and 4, we return the second one.
 '''

## 풀어보기
```
nodeList = []
 while head!=None:
     nodeList.append(head)
     head = head.next
 return nodeList[len(nodeList)//2]
```

## 회고

확실히 링크드리스트가 나한테 좀 약한 부분인 것 같다.  
오늘 간단히 기본기를 쌓았으니 더 공부해야겠다.
