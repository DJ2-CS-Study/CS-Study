# 거품 정렬 (Bubble Sort)

### 정렬 방식

1. 앞에서부터 현재 원소와 바로 다음 원소를 비교한다.
2. 현재 원소가 다음 원소보다 크면 원소를 교환한다.
3. 다음 원소로 이동하여 해당 원소와 그 다음 원소를 비교한다.

![img](https://blog.kakaocdn.net/dn/dfQeBw/btqT1848T64/H5D9U4z8dhELfRTkfk2k30/img.png)

### 시간 복잡도 

$$
\frac{n(n-1)}{2} => O(n^2)
$$

### 구현 코드

```python
def bubble_sort(A):
    for i in range(len(A)-1):
        for j in range(i,len(A)):
            if A[i]>A[j]:
                A[i],A[j] = A[j],A[i]
```



참조 : https://st-lab.tistory.com/195