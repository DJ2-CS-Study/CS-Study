# BFS (너비 우선 탐색)

>  그래프 탐색 : 어떤 것들이 연속해서 이어질 때, 모두 확인하는 방법
>
> Graph : Vertex(node) + Edge

#### BFS : 루트 노드 또는 임의 노드에서 인접한 노드부터 먼저 탐색하는 방법

큐를 통해 구현

### BFS의 특징

- 최소 비용 : 모든 곳을 탐색하는 것보다 최소 비용(최단 경로)이 우선일 때 적합

- 시간복잡도
  - 인접 행렬 : O(V^2)
  - 인접 리스트 : O(V+E)

- 재귀적으로 동작하지 않는다.
- 어떤 노드를 방문했었는지 반드시 검사 - 무한루프 방지
- 방문한 노드들을 차례로 저장한 후 꺼낼 수 있는 자료구조인 큐(Queue)를 사용
  - FIFO 선입선출 원칙
- 경로가 매우 길 경우에는 탐색 가지가 급격히 증가함에 따라 보다 많은 메모리를 필요로 하게 된다.

![img](https://gmlwjd9405.github.io/images/algorithm-dfs-vs-bfs/bfs-example.png)





참조 : https://gmlwjd9405.github.io/2018/08/15/algorithm-bfs.html