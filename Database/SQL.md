### SQL(Structured Query Language)
- 관계형 데이터 베이스 관리 시스템(RDMBS)의 데이터 관리를 위한 특수 목적 프로그래밍 언어
    - RDBMS 종류에 따라 문법이 조금씩 달라 질 수 있음
    - Oracle DB, MySQL, Maria DB, Postgre DB, SQL server, SQLite
- 자료의 검색, 관리, 테이터베이스 스키마 수정 등 작업
- SQL 명령어는 크게 4가지로 나뉨
    - DDL : 데이터베이스 스키마 설명을 처리하는 언어. 테이블 생성/변경/삭제 등
    - DML : 데이터 검색, 삽입, 변경, 삭제 수행
    - DCL : 데이터에 접근할 수 있는 권한을 관리하는 언어
    - TCL : 트랜잭션을 다루는 언어

| 종류 | 명령어                                                       |
| ---- | ------------------------------------------------------------ |
| DDL  | CREATE, ALTER, DROP, TRUNCATE, COMMENT, RENAME               |
| DML  | SELETE, INSERT, UPDATE, DELETE, MERGE, CALL , EXPLAIN PLAN, LOCK TABLE |
| DCL  | GRANT, REVOKE                                                |
| TCL  | COMMIT, ROLLBACK, SAVEPOINT, SET, TRASACTION                 |
