# 617. Merge Two Binary Trees

- 문제링크: https://leetcode.com/problems/merge-two-binary-trees/
- 난이도: Easy

You are given two binary trees root1 and root2.  

Imagine that when you put one of them to cover the other,  
some nodes of the two trees are overlapped while the others are not.  
You need to merge the two trees into a new binary tree.  
The merge rule is that if two nodes overlap,  
then sum node values up as the new value of the merged node.  
Otherwise, the NOT null node will be used as the node of the new tree.  

Return the merged tree.  

Note: The merging process must start from the root nodes of both trees.  

 

Example 1:

<img width="513" alt="image" src="https://user-images.githubusercontent.com/46602874/192311352-21be3de1-9639-48bc-81eb-2f4d9e495ba4.png">

```
Input: root1 = [1,3,2,5], root2 = [2,1,3,null,4,null,7]
Output: [3,4,5,5,4,null,7]
```

Example 2:

```
Input: root1 = [1], root2 = [1,2]
Output: [2,2]
``` 

Constraints:

- The number of nodes in both trees is in the range [0, 2000].
- -104 <= Node.val <= 104

# 풀어보기

문제를 한참 읽었다  
어떻게 저런 output이 나오는건지 이해가 되지 않았다.  
알고보니 같은 위치에 있는 left랑 right에 값이 있으면 더해주고,  
없으면 그 위치에 merge해주는 문제였다.

```
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def mergeTrees(self, root1: Optional[TreeNode], root2: Optional[TreeNode]) -> Optional[TreeNode]:
        if not root1:
            return root2
        if not root2:
            return root1
        root1.val += root2.val
        root1.left = self.mergeTrees(root1.left, root2.left)
        root1.right = self.mergeTrees(root1.right, root2.right)
        
        return root1
```

휴 문제 이해하는 게 어려웠다.  
잘 풀어서 다행이다~
