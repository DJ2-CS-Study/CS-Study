# Quick Sort(퀵 정렬)

### 정렬 방식

1. 리스트 안의 한 요소를 선택한다. 그 요소를 피벗(pivot)이라 한다.
2. 피벗을 기준으로 피벗보다 작은 요소를 왼쪽 리스트, 피벗보다 큰 요소를 오른쪽 리스트로 나눈다.
3. 피벗을 제외한 왼쪽과 오른쪽 부분리스트에서 다시 피벗을 정하고 각 리스트에 대해 위의 과정을 반복한다.
4. 더이상 분할이 불가능하면 끝

![img](https://t1.daumcdn.net/cfile/tistory/27436E4B5357290E2A)

### 시간 복잡도 : O(nlogn)

### 특징

- 장점
  - 다른 메모리 공간을 필요로 하지 않음(=제자리 정렬)
  - 시간 복잡도O(nlogn)을 가지는 알고리즘 중 가장 빠르다.
- 단점
  - 불안정 정렬이다.
  - 정렬된 배열에 대해서는 오히려 더 오래 걸린다. 최악의 경우 O(n^2)

### 구현 코드

```python
def partition(arr, l, h):
    pivot = arr[h]

    i = l-1
    for j in range(l,h):
        if arr[j]<pivot:
            i += 1
            arr[i],arr[j] = arr[j],arr[i]
    arr[i+1], arr[h] = arr[h], arr[i+1]
    return i+1

def quick(arr,l,h):
    if l < h:
        p = partition(arr,l,h)
        quick(arr,l,p-1)
        quick(arr,p+1,h)
    return arr

```





참조 : https://itstory.tk/entry/%ED%80%B5%EC%A0%95%EB%A0%ACQuick-Sort

​			https://gyoogle.dev/blog/algorithm/Quick%20Sort.html