# Radix Sort (기수정렬)

### 정렬 방식

1. 0~9 까지의 Bucket(Queue 자료구조) 준비.
2. 데이터 중, 가장 낮은 자리수에 해당하는 Bucket 인덱스에 수를 정렬.
3. 자리수를 증가시키고(1,10,100,1000,1000... ), 그 자릿수보다 작은 값을  Bucket 0에 정렬.
4. 2번과 3번 과정을 반복.

![img](https://images.velog.io/images/nathan29849/post/2f7a9326-c3fe-4a0f-9107-7ba37bac50e5/image.png)

### 시간복잡도 : O(n)

### 특징 

- 비교를 하지 않고 정렬하는 특이한 방식
- LSD와 MSD가 있음 ( LSD : 작은 자리수부터 정렬 진행, MSD : 큰 자릿수부터 정렬진행)
- 장점
  - 같은 두 수가 있어도 순서를 유지하는 안정 정렬
  - 빠른 성능
- 단점
  - 자릿수가 없는 것은 정렬할 수가 없다.(부동 소수점과 같은 것)
  - '버킷'이라는 추가적인 공간할당이 필요하며, 이 버킷의 역할을 하는 Queue는 매우 큰 용량을 필요로 한다.



### 구현 코드

```python
def radix_sort(A):
    size = len(A)
    maxval = max(A)
    standard = 1                                  # 기준값을 1,10,100,1000 순으로 증가시킴
    while standard <= maxval:                         # 기준값이 최대값보다 커질 때 정렬 끝
        output = [0]*size                             # 정렬된 데이터를 담을 배열
        count = [0]*10                                 
        for i in range(size):                         # 데이터를 자리수 별로 세 놓은 배열 [0~9 데이터갯수,10~99 데이터갯수,100~999 데이터갯수,...]
            count[(A[i]//standard)%10] += 1
        for i in range(1,10):                         # 위의 배열을 누적하여 저장 ex) [5,6,3] => [5,11,14]
            count[i]+=count[i-1]
        for i in range(size-1,-1,-1):                 
        	j = (A[i]//standard)%10                   # i 번째 데이터의 standard자리 값 ex) standard=10일때 10의 자리수
        	output[count[j]-1] = A[i]                 # 자리수별로 데이터 새로 배열 [0,100,10,20,1,1,31,22,22,42,4,224,355,9]
        	count[j] -= 1                                                         # [0,1,1,4,9,100,10,20,22,22,224,31,42,355] 한 자리수는 10의자리가 0이므로 제일 앞에 배열됨
        for i in range(size): A[i]=output[i]                                      # [0,1,1,4,9,10,20,22,22,31,42,100,224,355] 두 자리수는 100의자리가 0이므로 제일 앞에 배열됨
        standard *= 10                            # 기준값 자리수 증가시킴
arr = [9,1,22,4,0,1,22,100,10,224,355,42,31,20]
radix_sort( arr )
print( arr )
```





참조 : https://zetawiki.com/wiki/Python_%EA%B8%B0%EC%88%98%EC%A0%95%EB%A0%AC_%EA%B5%AC%ED%98%84

https://velog.io/@nathan29849/Python-Algorithm-class-%EA%B8%B0%EC%88%98%EC%A0%95%EB%A0%AC%EA%B3%BC-%EA%B3%84%EC%88%98%EC%A0%95%EB%A0%AC