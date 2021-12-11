### SELECT
하나 또는 그 이상의 테이블에서 데이터를 추출하는 DML 중 하나
SELECE -- FROM -- 의 기본 구조를 가지고, WHERE, GROUP BY, HAVING, ORDER BY 등 과 함께 사용

- 테이블의 모든 컴럼 선택

```SQL
SELECT * FROM CLASS
```

- 테이블의 특정 컬럼 선택, 별칭으로 불러오기

```SQL
SELECT STUDENT_ID FROM CLASS
SELECT STUDENT_ID AS ID FROM CLASS
```

- 정렬
    - ASC, DESC로 오름차순, 내림차순 지정 가능
    - ASC이 기본값
    - 여러 기준에 따라 정렬 할 때, ORDER BY를 여러 번 나열, 또는 컬럼 뒤 방식으로 지정 가능

```SQL
SELECT STUDENT_ID, STUDENT_NAME
FROM CLASS
ORDER BY STUDENT_ID

SELECT STUDENT_ID, STUDENT_NAME
FROM CLASS
ORDER BY STUDENT_ID DESC

SELECT STUDENT_ID, STUDENT_NAME
FROM CLASS
ORDER BY STUDENT_NAME, STUDENT_ID DESC
```

- 특정 조건에 따라 선택
    - =, <, >, <= , >=와 같은 연산자 사용 가능
    - LIKE를 활용하여 패턴 매칭 검색 가능, 이 때 와일드 카드 형식 필요

```SQL
SELECT STUDENT_ID, STUDENT_NAME
FROM CLASS
WHERE STUDENT_ID=5

SELECT STUDENT_ID, STUDENT_NAME
FROM CLASS
WHERE STUDENT_NAME LIKE '이%'
```



