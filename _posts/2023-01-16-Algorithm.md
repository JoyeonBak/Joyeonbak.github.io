---
layout: post
title: Greedy Algorithm
subtitle: 
categories: Algorithm
tags: [Algorithm, 알고리즘, GreedyAlgorithm, 그리디알고리즘]
--- 
## 알고리즘이란?
수학과 컴퓨터과학, 언어학 또는 엮인 분야에서 어떠한 문제를 해결하기 위해 정해진 일련의 절차이다.  
계산을 실행하기 위한 단계적 절차를 의미하기도 한다. 즉, 문제 풀이에 필요한 계산절차 또는 처리과정의 순서를 뜻한다.


### 그리디 알고리즘 *Greedy Algorithm*
* 탐욕법 또는 욕심쟁이 알고리즘
* 현재 상황에서 지금 당장 좋은 것만 고르는 방법
* 최단 경로 찾는 문제는 플로이드 워셜(Floyd-Warshall), 다익스트라(Dijkstra) 알고리즘 또는 팀 노트 준비 필요
* '가장 큰 순서대로', '가장 작은 순서대로'와 같은 기준을 종종 제시  
   *그럴 땐, 정렬 알고리즘을 미리 암기*


### 거스름돈
그리디 알고리즘의 대표 문제

Q. 거스름돈 사용할 동정 500원, 100원, 50원, 10원 짜리는 무한 존재. 손님에게 거슬러 줘야 할 돈이 N일 때, 동전의 최소 개수 (단, 거슬러 줘야할 돈 N은 항상 10의 배수)


```PYTHON
#가장 큰 화폐 단위부터 돈을 거슬러 주는 것이 포인트!
#입력으로 주어진 N이 1,260 일 때
n = 1260
count = 0

coin_types = [500, 100, 50, 10]

for coin in coin_types:
    count += n//coin #몫
    n %= coin #나머지

print(count)
```

***


### 큰 수의 법칙
Q. 주어진 배열의 수들을 M번 더하여 가장 큰 수 만들기 (단, K번을 초과해서 더해질 수 없다.)  
<span style="color:##f6f8fa"> *예, \[2,4,5,6,4\]에서 M은 8이고 K는 3일 때, 6+6+6+5+6+6+6+5 = 46 정답은 46이다.* </span>

```PYTHON
"""
N,M,K를 공백으로 구분하여 입력 받기
N = 배열 요소 수
M = 전체 덧셈 횟수
K = 한 숫자 당 덧셈 횟수
"""
n, m, k = map(int, input().split())
#N개의 수를 공백으로 구분하여 입력받기(주어진 배열)
data = list(map(int, input().split()))

#작은 수 ~ 큰 수로 정렬을 미리 하면 따로 비교할 필요가 없음!
data.sort()
first = data[n-1] 
second = data[n-2]
result = 0

while True:
    #가장 큰 수를 K번 반복 더하기
    for i in range(k):
        if m == 0:
            break
        result += first
        m -= 1
    if m == 0:
        break
    result += second
    m -= 1

print(result)
```

### 여기서 잠깐!
### input( ).split( ) 
### vs. map(int, input( ).split( )) 
### vs. list(map(int,input().split())) 구분

```PYTHON
data = input().split()
print(data)
#['1','2','55','6'] 
#입력 받은 값이 문자열 리스트로 저장

data = list(map(int,input().split()))
print(data)
#[1, 2, 55, 6] 
#입력 받은 값이 int 리스트로 저장

"""
list로 감싸지 않고 map만 쓰려면 입력 받은 여러 개의 값을 넣을 변수들을 같이 적어줘야 함
data = map(int, input().split()) => error
x, y, z = map(int, input().split) 
        => x = 첫번째 입력받은 값, y = 두번째 입력받은 값, z = 세번째 입력받은 값
"""
```