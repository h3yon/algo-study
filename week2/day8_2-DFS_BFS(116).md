# 116. Populating Next Right Pointers in Each Node

- 난이도: 미디움
- 문제링크: https://leetcode.com/problems/populating-next-right-pointers-in-each-node/

You are given a perfect binary tree where all leaves are on the same level,  
and every parent has two children. The binary tree has the following definition:  

```
struct Node {
  int val;
  Node *left;
  Node *right;
  Node *next;
}
```

Populate each next pointer to point to its next right node.  
If there is no next right node, the next pointer should be set to NULL.  

Initially, all next pointers are set to NULL.  

 

Example 1:

```
Input: root = [1,2,3,4,5,6,7]
Output: [1,#,2,3,#,4,5,6,7,#]
Explanation: Given the above perfect binary tree (Figure A), your function should populate each next pointer to point to its next right node, just like in Figure B. The serialized output is in level order as connected by the next pointers, with '#' signifying the end of each level.
```

Example 2:

```
Input: root = []
Output: []
 ```

Constraints:

- The number of nodes in the tree is in the range [0, 212 - 1].
- -1000 <= Node.val <= 1000

# 풀어보기 & 회고

와 이건.. 머리를 좀 써야하는 문제였다.

```python
"""
# Definition for a Node.
class Node:
    def __init__(self, val: int = 0, left: 'Node' = None, right: 'Node' = None, next: 'Node' = None):
        self.val = val
        self.left = left
        self.right = right
        self.next = next
"""

class Solution:
    def connect(self, root: 'Optional[Node]') -> 'Optional[Node]':
        if not root:
            return None
        queue = deque([root])
        while queue:
            right_node = None
            for _ in range(len(queue)):
                cur = queue.popleft()
                cur.next, right_node = right_node, cur
                if cur.right:
                    queue.extend([cur.right, cur.left])
        return root    
```

보자. root가 없으면 None을 리턴하는 부분이 필요하다.  
BFS로 사용할 것이고, 일단 queue를 돌면서,  
right_node를 초기화해주고, queue만큼 돌면서 cur을 설정해준다.  
cur의 next는 right_node로 해주고, right_node는 cur로 해준다.(1층은 당연히 null을 보고 있을테니까)  
cur에서 right가 있으면 queue에 담고 계속 돈다.  

와 이건 내가 더 공부해야겠다!  
그래도 재미있었다ㅎㅎㅜ




