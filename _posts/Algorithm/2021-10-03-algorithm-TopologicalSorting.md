---
title:  "위상정렬(Topological Sorting)"
excerpt: "위상정렬 알고리즘"

categories:
  - Algorithm
tags:
  - [알고리즘, 그래프, 위상 정렬]

toc: true
toc_sticky: true
 
date: 2021-10-03
last_modified_at: 2021-10-03
---

# 위상 정렬(Topological Sorting)
* 정렬 알고리즘의 일종으로, 순서가 정해져 있는 일련의 작업을 차례대로 수행해야 할 때 사용할 수 있는 알고리즘이다.
* 조금 더 이론적인 설명은, 사이클이 없는 방향 그래프의 모든 노드를 '방향성에 거스르지 않도록 순서대로 나열하는 것'을 의미한다.

![image](https://user-images.githubusercontent.com/70308853/135748549-b999acb6-56eb-442a-94c3-7e2a7f150a13.png)

## 진입차수와 진출차수
* 진입차수(Indegree) : 특정한 노드로 들어오는 간선의 개수
* 진출차수(Outdegree) : 특정한 노드에서 나가는 간선의 개수

![image](https://user-images.githubusercontent.com/70308853/135748580-200f67ff-877b-424c-9a1f-98085c32f325.png)

## 위상 정렬 동작
1. 진입차수가 0인 노드를 큐에 넣는다.
2. 큐가 빌 때까지 다음의 과정을 반복
    1. 큐에서 원소를 꺼내 해당 노드에서 나가는 간선을 그래프에서 제거
    2. 새롭게 진입차수가 0이 된 노드를 큐에 삽입

![image](https://user-images.githubusercontent.com/70308853/135748637-19944118-2a0a-4b8f-aa65-1db069ddd979.png)

![image](https://user-images.githubusercontent.com/70308853/135748642-612027b4-ed11-45a8-ab2d-728d4835644c.png)

![image](https://user-images.githubusercontent.com/70308853/135748713-a61001ea-8c0e-4112-8df1-8d385d6a1216.png)

![image](https://user-images.githubusercontent.com/70308853/135748656-06c172b0-049f-42f0-b963-43eb63854be9.png)

![image](https://user-images.githubusercontent.com/70308853/135748667-8c3178aa-ec67-4063-a3a3-2aa66d8cb06a.png)

![image](https://user-images.githubusercontent.com/70308853/135748672-0cf1da63-441c-43c5-ba46-5346d95d7e53.png)

![image](https://user-images.githubusercontent.com/70308853/135748677-438f6ff9-9ba6-42c9-b3ba-816a7fc1e2fb.png)

![image](https://user-images.githubusercontent.com/70308853/135748682-f40c64e4-1a14-4136-8bbf-47f63e463a15.png)

![image](https://user-images.githubusercontent.com/70308853/135748687-a29e2078-e091-4bc1-83e9-0bc926897b43.png)

![image](https://user-images.githubusercontent.com/70308853/135748733-7657077a-3426-4a62-bdb8-53536d0a85d6.png)

## 위상 정렬의 특징
* 위상 정렬은 사이클이 없는 방향 그래프 (DAG)에 대해서만 수행할 수 있다.

      ※ DAG (Direct Acyclic Graph) : 순환하지 않는(=사이클이 없는) 방향 그래프
* 위상 정렬에서는 여러 가지 답이 존재할 수 있다. 한 단계에서 큐에 새롭게 들어가는 원소가 2개 이상인 경우가 있다면 여러 가지 답이 존재할 수 있다는 의미이다.
* 모든 원소를 방문하기 전에 큐가 비게 된다면 사이클이 존재한다고 판단할 수 있다. 왜냐하면 사이클에 포함된 원소 중에서 해당되는 어떠한 원소도 큐에 들어가지 못하게 되기 때문이다.
* 보통 큐로 구현하나, 스택을 이용한 DFS를 이용해 위상 정렬을 구현할 수도 있다.
* 시간 복잡도는 O(V+E)

      위상 정렬을 수행할 때는 차례대로 모든 노드를 확인하면서 (O(V)), 해당 노드에서 출발하는 간선을 차례대로 제거(O(E))해야 한다. 따라서 노드와 간선을 모두 확인하는 것을 고려하여 O(V) + O(E) = O(V+E)의 시간이 소요된다.


