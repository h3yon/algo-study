# 균형잡힌 세상

- 링크: https://www.acmicpc.net/problem/4949


'''
while True :
    s = input()
    stack = []

    if s == "." :
        break

    for i in s :
        if i == '[' or i == '(' :
            stack.append(i)
        elif i == ']' :
            if len(stack) != 0 and stack[-1] == '[' :
                stack.pop()
            else : 
                stack.append(']')
                break
        elif i == ')' :
            if len(stack) != 0 and stack[-1] == '(' :
                stack.pop()
            else :
                stack.append(')')
                break
    if len(stack) == 0 :
        print('yes')
    else :
        print('no')

'''

스택을 좋아하는 편이 아니라서  
그다지 좋아했던 문제는 아니었지만.  
그래도 좀 사용하게 돼서 좋았다!
