# 리모컨

- 링크: https://www.acmicpc.net/problem/1107
- 난이도: Gold V

## 문제

수빈이는 TV를 보고 있다. 수빈이는 채널을 돌리려고 했지만, 버튼을 너무 세게 누르는 바람에, 일부 숫자 버튼이 고장났다.  
리모컨에는 버튼이 0부터 9까지 숫자, +와 -가 있다. +를 누르면 현재 보고있는 채널에서 +1된 채널로 이동하고, -를 누르면 -1된 채널로 이동한다.  
채널 0에서 -를 누른 경우에는 채널이 변하지 않고, 채널은 무한대 만큼 있다.  
수빈이가 지금 이동하려고 하는 채널은 N이다. 어떤 버튼이 고장났는지 주어졌을 때,  
채널 N으로 이동하기 위해서 버튼을 최소 몇 번 눌러야하는지 구하는 프로그램을 작성하시오. 
수빈이가 지금 보고 있는 채널은 100번이다.  

## 입력

첫째 줄에 수빈이가 이동하려고 하는 채널 N (0 ≤ N ≤ 500,000)이 주어진다.  
둘째 줄에는 고장난 버튼의 개수 M (0 ≤ M ≤ 10)이 주어진다.  
고장난 버튼이 있는 경우에는 셋째 줄에는 고장난 버튼이 주어지며, 같은 버튼이 여러 번 주어지는 경우는 없다.

```
5457
3
6 7 8
```

## 출력
첫째 줄에 채널 N으로 이동하기 위해 버튼을 최소 몇 번 눌러야 하는지를 출력한다.

```
6
```

## 풀어보기

문제를 계속 보면 볼수록 이해가 안 됐다ㅎㅎ  
5457인데 어떻게 6이지? 이런 생각을 계속 하고 있었는데,  
6,7,8이 고장났으니까 리모컨으로 5455 입력 후, +, + 총 3번 입력하여 5457이 되는 걸 알 수 있다.  
5455(4번), +(1번), +(1번) 눌러서 총 6번을 누르는 문제였다.  

```python
min_cnt = 1e9
num_int = 0
btn_set = {i for i in range(0, 10)}

def find(num):
    global min_cnt, num_int, btn_set
    for btn in btn_set:
        tmp = num + str(btn)
        min_cnt = min(min_cnt, abs(num_int - int(tmp)) + len(tmp))

        if len(tmp) < 6:
            find(tmp)

def main():
    global min_cnt, num_int, btn_set
    num_int = int(input())
    n = int(input())
    min_cnt = min(min_cnt, abs(100 - num_int)) # 채널 이동 갯수
    btn_set -= set(map(int, input().split(' '))) if n else set()

    find('') if n < 10 else ''
    print(min_cnt)

main()
```

ㅎㅎ근데 고려해야 할 게 정말 많음을 깨달았다.  
오늘은 못 풀었지만 다시 한번 풀어봐야겠다.
