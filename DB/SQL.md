# SQL

### 1. SQL

> Structured Query Language

#### 1.1 정의

![img](https://t1.daumcdn.net/cfile/tistory/99491C4C5A47C7BF0B)

RDBMS에 저장된 데이터를 관리하기 위해 특수 목적으로 설계된 프로그래밍 표준 `언어`. SQL 문법은 영어와 유사하게 만들어져서 쉽게 읽고 쓰고 해석할 수 있다. SQL문을 통하여 기본 CURD를 수행 할 수 있다. SQL은 국제 표준화기구에서 표준을 정해서 발표가 되는데, DBMS를 만드는 회사가 여러 곳이기 때문에 모든 회사의 제품을 포용하지는 못한다.

![DBMS 제품](http://hongong.hanbit.co.kr/wp-content/uploads/2021/11/DBMS-%EC%A0%9C%ED%92%88.png)



<br>

#### 1.2 역할

* 데이터베이스 스키마, 테이블 생성 및 수정
* 자료의 검색 및 관리
* 데이터베이스 객체 접근 조정 관리

<br>

#### 1.3 SQL 분류

| 분류                                                         | 개념                                                         | 예시                                            |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ----------------------------------------------- |
| **DDL** - 데이터 정의 언어<br />(Data Definition Language)   | 관계형 데이터베이스 구조(테이블, 스키마)를 정의하기 위한 명령어 | **CREATE<br />DROP<br />ALTER**                 |
| **DML** - 데이터 조작 언어<br />(Data Manipulation Language) | 데이터를 저장, 조회, 수정, 삭제 등을 하기 위한 명령어        | **INSERT<br />SELECT<br />UPDATE<br />DELETE**  |
| **DCL** - 데이터 제어 언어<br />(Data Control Language)      | 데이터베이스 사용자의 권한 제어를 위해 사용하는 명령어       | **GRANT<br />REVOKE<br />COMMIT<br />ROLLBACK** |

<br>

> **SQL과 MySQL의 차이는?**
> SQL은 쿼리 언어 그 자체, MySQL은 ORACLE사가 개발한 RDBMS

<br>

#### 1.4 SQL 규칙(문법)

1. 명령은 항상 `;`(세미콜론)으로 마무리
2. 단일라인 주석은 `--`. 블록 주석은 `/**/`로 감싸서 사용
3. 보통 대 소문자를 가리지는 않지만 명령문은 대문자, 컬럼이름, db이름 등은 소문자로 하는것이 일반적

<br>

------

[참고1]: https://hongong.hanbit.co.kr/%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%B2%A0%EC%9D%B4%EC%8A%A4-%EC%9D%B4%ED%95%B4%ED%95%98%EA%B8%B0-databasedb-dbms-sql%EC%9D%98-%EA%B0%9C%EB%85%90/

