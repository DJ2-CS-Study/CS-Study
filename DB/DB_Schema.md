# 스키마(Schema)

> 스키마는 데이터베이스에서 자료의 구조, 자료의 표현 방법, 자료 간의 관계를 형식 언어로 정의한 구조이다. DBMS가 주어진 설정에 따라 데이터베이스 스키마를 생성하며, 데이터베이스 사용자가 자료를 저장, 조회, 삭제, 변경할 때 DBMS는 자신이 생성한 데이터베이스 스키마를 참조하여 명령을 수행한다.

**한마디로 데이터베이스의 구조와 제약조건(개체, 속성, 관계)에 관하여 전반적인 명세를 작성한 것**

### 1. 스키마의 특징

1. 스키마는 데이터 사전(시스템 전체에서 나타나는 데이터 항목들에 대한 정보를 지정한 중앙 저장소)에 저장되며 메타데이터라고도 한다.
2. 현실 세계의 특정한 한 부분의 표현으로서 특정 데이터 모델을 이용하여 만들어진다.

3. 시간에 따라 불변인 특성을 가진다.

4. 데이터의 구조적 특성을 의미하며 인스턴스(데이터베이스에 실제로 저장된 값)에 의해 규정된다.

<br>

### 2. 스키마의 구조

![img](DB_schema.assets/schema)![img](https://blog.kakaocdn.net/dn/lNIMd/btqQwocyYld/1vg6iP6ttEN7N680btgQo0/img.png)

스키마는 **<u>사용자의 관점</u>**에 따라 3개의 스키마로 나눠진다. DBMS는 외부적 스키마에 따라 명시된 사용자의 요구를 개념적 스키마에 적합한 형태로 변경하고 이를 다시 내부적 스키마에 적합한 형태로 변환한다.

<br>

#### 2.1 외부 스키마 (= 사용자 뷰)

* 외부스키마는 사용자나 프로그래머가 각 개인의 입장에서 필요로 하는 데이터베이스의 논리적 구조를 정의 한 것
* 외부스키마는 전체 데이터베이스의 한 논리적인 부분으로 볼 수 있으므로 서브 스키마라고도 한다.
* 하나의 DBMS에는 여러개의 외부스키마가 존재할 수 있으며 하나의 외부 스키마를 여러개의 응용프로그램이나 사용자가 공용으로 사용할 수 도 있다.
* 같은 데이터베이스에 대해서도 서로 다른 관점을 정의할 수 있다.
* 일반 사용자는 질의어(SQL)을 이용하여 DB를 쉽게 사용할 수 있다.
* 응용프로그래머는 C, JAVA 등의 언어를 이용하여 DB에 접근한다.

<br>

#### 2.2 개념 스키마 (= 전체적인 뷰)

* 개념스키마는 데이터베이스의 전체적인 논리적 구조이자 모든 응용 프로그램이나 사용자들이 필요로 하는 데이터를 종합한 조직 전체의 데이터베이스이다. 이는 하나만 존재한다.
* 개념스키마는 개체간의 관계와 제약 조건을 나타내고 데이터베이스의 접근 권한, 보안 및 무결성 규칙에 관한 명세를 정의한다.
* 데이터베이스 파일에 저장되는 데이터의 형태를 나타낸 것으로 단순히 스키마 라고 하면 보통 개념 스키마를 의미한다.
* 기관이나 조직의 관점에서 데이터베이스를 정의한 것이다.
* 데이터베이스 관리자에 의해 구성된다.

<br>

#### 2.3 내부 스키마 (= 저장 스키마)

* 내부스키마는 물리적 저장장치의 입장에서 본 데이터베이스 구조이다.
* 실제로 데이터베이스에 저장될 레코드의 물리적인 구조를 정의하고, 저장 데이터의 항목의 표현방법, 내부 레코드의 물리적 순서 등을 나타낸다.
* 시스템 프로그래머나 시스템 설계자가 보는 관점의 스키마이다.

<br>