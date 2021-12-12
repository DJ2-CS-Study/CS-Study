# MST

### Spanning Tree

그래프 내의 모든 정점을 포함하는 트리

### MST : Minimum Spanning Tree = 최소 신장 트리

### MST의 특징

1. 간선의 가중치의 합이 최소여야 한다.
2. n개의 정점을 가지는 그래프에 대해 반드시 (n-1)개의 간선만을 사용해야 한다.
3. 사이클이 포함되어서는 안된다.

---

## MST 구현 알고리즘

### 1. Kruskal

1. 그래프의 간선들을 가중치의 오름차순으로 정렬
2. 정렬된 간선 리스트에서 순서대로 사이클을 형성하지 않는 간선을 선택
3. MST의 집합에 추가

#### 시간 복잡도

정렬에 의해 좌우되므로 퀵 정렬과 같은 효율적인 알고리즘으로 O(ElogE)

![Kruskal Example](https://www.apexcel.blog/static/cd78191e47194535a5557f56775aeef8/f058b/kruskal.png)

![Kruskal Example](https://www.apexcel.blog/static/ce5737b01a97e8370509dd7cec4039d5/db783/k8.png)

#### 구현코드

```python
def find_set(x):
    while x != p[x]:
        x=p[x]
    return x

def union(x,y):
    p[find_set(x)] = find_set(y)
    
while cnt<N:
    n1=edges[idx][1]      # [가중치,노드1,노드2] 형식으로 들어옴
    n2=edges[idx][2]
    if find_set(n1) != find_set(n2):
        union(n1,n2)                # n1의 대표 노드가 n2의 대표노드를 가리키게 함
        ans += edges[idx][0]
        cnt += 1
    idx += 1

```



### 2. Prim

1. 시작 정점만을 MST 집합에 포함
2. 앞 단계에서 만들어진 MST 집합에 인접한 정점들 중에서 최소 비용의 정점을 선택하여 트리를 확장
   즉, 가장 낮은 가중치 먼저 선택
3. 위의 과정을 트리가 (N-1)개의 간선을 가질 때까지 반복

#### 시간 복잡도

정점의 수 n만큼 반복하며, 내부 반복문이 n번 반복하므로 O(V^2)

![Prim Example](https://www.apexcel.blog/static/f9daf3a707041edec1cfcf757a174988/f058b/prim1.png)



![Prim Example](https://www.apexcel.blog/static/1655b5226f18fda63fe7c41074a2b633/f058b/prim2.png)

![Prim Example](https://www.apexcel.blog/static/414bc42403d3b69fb86af5b93f17e3df/f058b/prim3.png)

![Prim Example](https://www.apexcel.blog/static/a8ae916bb969104c34a7e94a376ca12f/db783/prim-result.png)

#### 구현코드

인접 행렬 형태의 Input

```python
def prim(start,V):
    MST[start] = 0          # 임의의 시작점 간선비용을 0으로 세팅
    cost = 0              
    for i in range(V+1):   
        minV = INF
        minVertex = -1          # 최소 간선비용의 정점번호
        for j in range(V+1):
            if not visited[j] and minV>MST[j]:
                minV = MST[j]
                minVertex = j
        visited[minVertex] = 1
        cost += minV               # 간선비용 누적

        for j in range(V+1):        # 2. 선택된 정점 기준으로 신장트리에 연결되지 않은 타 정점과의 간선 비용 최소로 업데이트
            if not visited[j] and arr[minVertex][j] != 0 and MST[j] > arr[minVertex][j]:
                MST[j] = arr[minVertex][j]
    return cost

```



### 참고 : 

https://gmlwjd9405.github.io/2018/08/28/algorithm-mst.html

https://www.apexcel.blog/algorithm/graph/mst/mst/