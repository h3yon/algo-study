# 설탕배달

- 링크: https://www.acmicpc.net/problem/2839

'''

num = int(input())
count = 0

while num>=3 :
    if not(num%5) : # 5의 배수이면
        count+= num/5
        break
    else :
        count+=1
    num-=3

if num==1 or num==2:
    count = -1
else :
    count += 0

print(int(count))
'''

힐링되는 문제였다ㅎㅎ
슬슬 클래스2로 올라가면 될 것 같다~
