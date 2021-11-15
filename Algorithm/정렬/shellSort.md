# ShellSort(셸 정렬)

### 정렬 방식

> 일정 간격 떨어져 있는 원소들끼리 부분 집합을 구성한 후, 각 부분집합 원소들에 대해서 삽입 정렬(insertionSort)을 수행하되, 간격을 줄여가며 삽입 정렬을 반복하여 전체 원소들을 정렬하는 방식 
>
> 삽입정렬을 베이스로 함.

1. 간격 h = 정렬할 배열의 길이 % 2
2. h만큼 간격이 있는 원소들의 부분집합을 만듦
3. 각 부분집합을 삽입 정렬
4. 간격을 h = h//2 로 바꿔준 후 2, 3 과정을 h가 0이 될 때까지 반복

![img](https://gmlwjd9405.github.io/images/algorithm-shell-sort/shell-sort.png)



### 시간복잡도 : O(N^1.5)

### 특징

- 삽입 정렬에서 역순 형태일 때, 비교횟수가 큰 단점을 보완하기 위해 고안해 냄.
- 최선일 때 O(n) 평균 O(n) 최악 O(n^2) 의 시간복잡도를 가진다.
- 장점
  - 연속적이지 않은 리스트의 자료 교환이 일어나면 더 큰 거리를 이동
    - 교환되는 요소들이 최종 위치에 가까워짐
- 단점
  - 간격에 따라 성능이 매우 나빠질 수 있다.

### 구현 코드

```python
def insertionSort(arr,first,last,h):
    i = first+h
    while i<last:
        val = arr[i]
        pos = i
        while pos>first and arr[pos-h]>val:
            arr[pos] = arr[pos-h]
            pos -= h
        arr[pos] = val
        i += h

def shellSort(arr):
    n = len(arr)
    h = n//2
    if not h%2:     # 간격은 홀수로 하는 것이 좋음
        h += 1  
    while h > 0:
        for i in range(0,h+1):
            insertionSort(arr,i,n,h)
        h //= 2
    return arr
arr = [10, 8, 6, 20, 4, 3, 22, 1, 0, 15, 16]

print(shellSort(arr))
```

참조 : https://mong9data.tistory.com/45

https://gmlwjd9405.github.io/2018/05/08/algorithm-shell-sort.html