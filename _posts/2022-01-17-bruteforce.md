---
layout: single
title:  "완전탐색(exhaustive search) Brute-force"
categories:
  - 알고리즘
tags:
  - 알고리즘
  - 완전탐색
  - 브루스포스
last_modified_at: 2022-01-18T13:18:00-00:00
---

## 2. 완전탐색(exhaustive search) : Brute-force

완전탐색(exhaustive serach)는 말 그대로 '모든 경우의 수를 찾아서 답을 찾는 방법'이다. 가장 강력하고 확실한 방법이지만 시간이가장 오래걸리는 탐색 기법이다.


### 완전탐색의 종류

- Brute-force
- 비트마스크
- 순열
- 백트래킹
- DFS, BFS

완전탐색 자체는 알고리즘이 아니기 때문에 완전탐색기법을 사용하기위해서 여러가지  알고리즘이 이용된다.
오늘은 이중에서 Brute-force만 다룰 것이다.

###  Brute-force란?

'무식한 힘' 뜻 그대로 무식하게 푸는 기법이다. 어떠한 특정한 기법을 사용하지 않고 단순히 for문 if문 등으로 모든 케이스를 만들어 답을 만들어 구한다.


### 어떤 경우에 사용할까?

보통 완전 탐색 문제는 난이도가 쉬운편이다. 하지만 미쳐 생각지도 못했던 난이도 있는 문제에서 활용해야 하는 경우가 있다.


1. 입력으로 주어지는 데이터(N)의 크기가 매우작다.
   다른 알고리즘 문제에 비해 완전 탐색 문제는 시간복잡도가 크기 떄문에 ex)부분집합, 순열-> O(2^N), O(N!)  N의 크기가 매우작다.
2. 출력해야하는 값의 범위가 작아서 입력값N이 크더라도 역추적할수 있를때 사용한다.
   
3. 어떠한 문제의 조건을 고정시켯을때 풀이가 간단해지는 경우(완전탐색+그리디)
   

### 관련 문제

- [BOJ 2309 일곱난쟁이](https://hong1995.github.io/boj/BOJ2309/)  
  <https://www.acmicpc.net/problem/2309>
- [BOJ 2231 분해합](https://hong1995.github.io/boj/BOJ2231/)  
  <https://www.acmicpc.net/problem/2231>
- [BOJ 3085 사탕게임 ](https://hong1995.github.io/boj/BOJ3085/)  
  <https://www.acmicpc.net/problem/3085>
- [BOJ 10448 유레카 이론](https://hong1995.github.io/boj/BOJ10448/)  
  <https://www.acmicpc.net/problem/10448>
- [BOJ 2503 숫자 야구 ](https://hong1995.github.io/boj/BOJ2503/)  
  <https://www.acmicpc.net/problem/2503>
- [BOJ 1018 체스판 다시 칠하기 ](https://hong1995.github.io/boj/BOJ1018/)  
  <https://www.acmicpc.net/problem/1018>
- [BOJ 1182 부분집합의 합](https://hong1995.github.io/boj/BOJ1182/)  
  <https://www.acmicpc.net/problem/1182>
