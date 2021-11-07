# Insertion Sort(삽입 정렬)

### 정렬 방식

- 두 번째 자료부터 시작하여 그 앞의 자료들과 비교하여 지정된 자리에 자료를 삽입하여 정렬



![img](https://gmlwjd9405.github.io/images/algorithm-insertion-sort/insertion-sort.png)

### 시간 복잡도

정렬 되어 있는 경우 : O(n)

입력자료가 역순인 경우 (최악) : O(n^2)

### 특징

- 장점
  - 알고리즘이 단순하다.
  - 대부분의 원소가 이미 정렬되어 있는 경우 매우 효율적일 수 있다.
  - 다른 메모리 공간을 필요로 하지 않는다. 
  - 안정 정렬(stable sort)이다.
    - 안정 정렬 : 중복된 값을 입력된 순서와 동일하게 유지해서 정렬
  - 선택 정렬이나 거품 정렬에 비해 상대적으로 빠르다
- 단점
  - 최악의 시간복잡도가 O(n^2)으로 비효율적이다.
  - 배열의 길이가 길어질 수록 비효율적이다.

### 구현 코드

```python
def insertion(A):
    for i in range(1,len(A)):
        j=i-1
        target = A[i]
        while (j>=0 and target<A[j]): # 작은 수를 만날 때까지 인덱스 감소
            j -= 1
        A.insert(j+1,target)            # 현재 값(A[i])보다 작은 수의 인덱스에 값을 삽입하고           
        del A[i+1]                    # 삭제
    return A
```

참조 : https://gmlwjd9405.github.io/2018/05/06/algorithm-insertion-sort.html