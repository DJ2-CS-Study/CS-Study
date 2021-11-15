# HeapSort(힙 정렬)

### 정렬 방식

- 최대 힙 트리나 최소 힙 트리를 구성해 정렬하는 방법. 

1. 최대힙 만들기
2. 루트 노드(=1번 노드=최대값)를 말단(최하위)으로 보내고 자리 확정.
3. 확정된 노드를 제외하고 최대힙 만들기
4. 위의 과정 반복.



![image-20211111220439300](heapSort(notfinished).assets/image-20211111220439300.png)

![image-20211111220545069](heapSort(notfinished).assets/image-20211111220545069.png)



### 시간복잡도 : O(nlogn)

### 특징

- 장점
  - 최댓값, 최솟값을 쉽게, 빠르게 추출할 수 있는 자료구조.
  - 전체 자료를 정렬하는 것보다 가장 큰 값 몇 개만 필요할 때 유용
- 단점
  - 같은 값의 순서가 바뀔 수 있는 불안정 정렬이다.

### 구현 코드

```python
def heap(A,k): # 최대힙 만들기
    for i in range(2,k):
        while 1<i and A[i] > A[i//2]:
            A[i], A[i//2] = A[i//2], A[i]
            i //= 2
def heapSort(A): 
    n = len(A) 
    for i in range(n, 1, -1): 
        heap(A, i)                  # 확정된 값 이전 까지 최대힙정렬
        A[1],A[i-1] = A[i-1],A[1]   # 루트 노드 끝으로 보내기
arr = [0]+[1,32,22,31,96,63,21,85,45,76] 
heapSort(arr) 
print(arr)
```





참조 : https://yjg-lab.tistory.com/169?category=956502

