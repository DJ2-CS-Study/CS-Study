# Selection Sort (선택 정렬)

### 정렬 방식

1. 주어진 배열 중 최솟값을 찾는다.
2. 그 값을 맨 앞에 위치한 값과 교체한다.
3. 두 번째 원소부터 최솟값을 찾는다.
4. 그 값을 두 번째 위치한 값과 교체한다.
5. 하나의 원소만 남을 때까지 반복한다.

![img](https://gmlwjd9405.github.io/images/algorithm-selection-sort/selection-sort.png)

### 시간 복잡도 : O(n^2)

### 특징

- 장점
  - 단순하고 쉽다.
  - 자료 이동 횟수가 미리 결정
- 단점
  - 불안정 정렬 ( 같은 값을 가질 때, 입력 순서가 바뀔 수 있다.)

### 구현 코드

```python
def selection_sort(arr):
    for i in range(len(arr) - 1):
        min_idx = i
        for j in range(i + 1, len(arr)):
            if arr[j] < arr[min_idx]:
                min_idx = j
        arr[i], arr[min_idx] = arr[min_idx], arr[i]
```



참조 : https://gmlwjd9405.github.io/2018/05/06/algorithm-selection-sort.html,

https://www.daleseo.com/sort-selection/