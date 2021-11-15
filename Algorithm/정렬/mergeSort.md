# Merge Sort(병합 정렬)

### 정렬 방식

1. 리스트의 길이가 0 or 1이면 이미 정렬된 것으로 본다.

2. 정렬되지 않은 리스트를 절반으로 잘라 두 부분 리스트로 나눈다.

3. 각 부분 리스트를 길이가 1일때까지 분할한다.

4. 두 부분 리스트들을 합병 정렬을 이용해 정렬한다.

   

![img](https://gmlwjd9405.github.io/images/algorithm-merge-sort/merge-sort-concepts.png)

### 시간복잡도 : O(nlogn)

### 특징

- 장점
  - 안정정렬이다.
  - 데이터 분포에 영향을 덜 받는다. (정렬 시간이 O(nlogn)으로 동일)
  
  ※ 참고
  
  - 만약 레코드를 연결 리스트(Linked List)로 구성하면, 링크 인덱스만 변경되므로 데이터의 이동은 무시할 수 있을 정도로 작아진다.
    - 제자리 정렬 가능(=다른 메모리 공간을 필요로하지 않음)
  - 따라서 크기가 큰 레코드를 정렬할 경우에 연결 리스트를 사용한다면, 합병 정렬은 퀵 정렬을 포함한 다른 어떤 졍렬 방법보다 효율적이다.
  
- 단점
  - 병합을 배열로 구성하면, 임시 배열이 필요하며, 이동 횟수가 많아 시간적 낭비를 초래.
    - 제자리 정렬이 아님 => 메모리 활용이 비효율적

### 코드 구현

```python
def lining(arr):
    if len(arr)==1:
        return arr
    length = len(arr)
    mid = length//2
    left = lining(arr[:mid])
    right = lining(arr[mid:])
    l = len(left)
    r = len(right)
    i = j = 0
    merged_arr = []
    while i < l and j < r:
        if left[i] > right[j]:
            merged_arr.append(right[j])
            j += 1
        else:
            merged_arr.append(left[i])
            i += 1
    merged_arr += right[j:]
    merged_arr += left[i:]
    return merged_arr
```



참조 : https://gmlwjd9405.github.io/2018/05/08/algorithm-merge-sort.html