# DFS(깊이 우선 탐색)

#### DFS : 루트 노드 혹은 임의 노드에서 다음 브랜치로 넘어가기 전에, 해당 브랜치를 모두 탐색하는 방법

### DFS의 특징

- 모든 경로를 방문해야 할 경우 적합

- 시간복잡도
  - 인접 행렬 : O(V^2)
  - 인접 리스트 : O(V+E)

- 현 경로상의 노드들만 기억하면 되므로 저장공간의 수요가 비교적 적다.
- 해가 없는 경로에 깊이 빠질 가능성이 있다.
- 최적의 해를 구하지 않는다.
- 순환 호출 또는 스택으로 구현

![img](https://gmlwjd9405.github.io/images/algorithm-dfs-vs-bfs/dfs-example.png)



```
def DFS(n):
    print(n,end=" ")
    visit[n] = True
    for i in sorted(adj_list[n]):
        if not visit[i]:
            DFS(i)

def BFS(n):
    q = [n]
    visit[n] = True
    while q:
        t = q.pop(0)
        print(t,end=" ")
        for i in sorted(adj_list[t]):
            if not visit[i]:
                q.append(i)
                visit[i] = True

N,M,V = map(int,input().split())
adj_list = [[] for _ in range(N+1)]
for _ in range(M):
    n1,n2 = map(int,input().split())
    adj_list[n1].append(n2)
    adj_list[n2].append(n1)
visit = [True]+[False]*N
DFS(V)
print()
visit = [True]+[False]*N
BFS(V)

```



출처 : https://gmlwjd9405.github.io/2018/08/14/algorithm-dfs.html

