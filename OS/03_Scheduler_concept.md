# Scheduler

---

## 1. 스케줄러란?

한정된 메모리를 이용해서 여러 프로세스를 효율적으로 수행할 수 있도록 실행할 수 있는(실행해야 하는) 프로세스 중 하나를 선택하는 것

> 종류
>
> - 장기 스케줄러
> - 단기 스케줄러
> - 중기 스케줄러

<br>

## 2. Scheduling Queue

- Job Queue : 현재 시스템 내에 있는 모든 프로세스의 집합
- Ready Queye : 메인 메모리 안에 상주하는 모든 프로세스의 집합
- I/O 장치 사용을 대기하는 프로세스의 집합

<br>

## 3. 스케줄러의 종류

![img](https://blog.kakaocdn.net/dn/dx93lz/btqD4yMy23U/3d1x1IKnGEaV5WCBpbTmBK/img.png)

> ### 장기 스케줄러 (Job scheduler)
>
> - 잡 풀(Job Pool)에서 프로세스들을 선별하여 메인 메모리에 적재하는 스케줄러
>
> - 메모리와 디스크 사이의 스케줄링을 담당
>
>   > 여기서 메모리란 **메인 메모리**를 의미하고 디스크란 보통 **프로그램이 저장되어 있는 대용량 메모리**를 의미합니다
>
> - 메모리에 몇 개의 프로세스를 올릴지 제어
>
> <br>
>
> ### 단기 스케줄러 (CPU scheduler)
>
> - 장기 스케줄러가 Ready Queue에 적재해놓은 프로세스를 CPU로 적재하는 스케줄러
> - 메모리와 CPU 사이의 스케줄링을 담당
>
> <br>
>
> ### 중기 스케줄러 (Swapper)
>
> - 메모리에 여유 공간을 만들기 위해 메모리에 있는 프로세스를 디스크로 보내는 역할
> - 즉, 메모리에 너무 많은 프로세스가 적재되지 않도록 조절하는 스케줄러
