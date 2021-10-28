### 관계모델
관계라는 개념을 사용해 표현한 데이터 모델
하나 이상의 관계(relations)의 집합으로, 행(row, tuples)와 열(column, attributes)로 구성

- 관계(릴레이션, relations) : 관계 모델에서 데이터를 표현하는 주된 구성자. 릴레이션 스키마(relation schema)와 릴레이션 인스턴스(realation instance)로 구성
  - 릴레이션 인스턴스 : 테이블
  - 릴레이션 스키마 : 테이블읠 열(필드)를 기술

### (SQL) 관계 생성, 수정
#### [Django 코드 확인](DB%20with%20Django/DTL%20CRUD.md)
- 테이블 생성
```sql
CREATE TABLE classmates (
  id INTEGER PRIMARY KEY
  name TEXT
  age INT
  address TEXT
);
```
- 테이블 삭제
```sql
DROP TABLE classmates;
```
- Create
```sql
INSERT INTO 테이블이름 (컬럼1, 컬럼2, ...) VALUES (값1, 값2, ...);
INSERT INTO classmates (name, age) VALUES ('홍길동', 20);
-- 모든 열의 데이터를 입력하는 경우 컬럼을 지정하지 않아도 됨
INSERT INTO classmates VALUES ('홍길동', 20, '대구');
```
- Read
```sql
-- 부분 조회 / 전체 조회
SELECT 컬럼1, 컬럼2, ... FROM 테이블이름;
SELECT * FROM 테이블이름;
-- LIMIT : 원하는 수 만큼 데이터 조회
SELECT 컬럼1, 컬럼2, ... FROM 테이블이름 LIMIT 숫자;
-- OFFSET : 조회를 시작하는 컬럼 지정
SELECT 컬럼1, 컬럼2, ... FROM 테이블이름 LIMIT 숫자 OFFSET 숫자;
-- WHERE : 특정 조건 조회
SELECT 컬럼1, 컬럼2, ... FROM 테이블이름 WHERE 조건;
SELECT rowid, name FROM classmates WHERE address='서울';
-- DISTINCT : 중복 없이 조회
SELECT DISTINCT 컬럼 FROM 테이블이름;
```
- DELETE
```sql
DELETE FROM 테이블이름 WHERE 조건;
```
- UPDATE
```sql
UPDATE 테이블이름 SET 컬럼1=값1, 컬럼2=값2, ... WHERE 조건;
```

#### WHERE 응용

#### LIKE