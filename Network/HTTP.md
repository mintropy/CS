### HTTP (HyperText Transfer Protocol)
- 웹 상에서 컨텐츠를 전송하기 위한 규칙, 약속
- 모든 데이터 교환은 요청(request)와 응답(response)로 이루어짐
- Stateless, Connectless 특징을 가짐
- 각 리소스는 URI(Uniform Resource Identifier)로 식별
  - 통합 자원 식별자
  - URI는 URL과 URN으로 나눌 수 있음
  - URL(Uniform Resource Locator)
    - 통합 자원 위치
    - 네트워크 상 자원이 어디에 있는지
  - URN(Uniform Resource Name)
    - 통합 자원 이름
  - URI구조
        1. scheme(protocol) : 브라우저가 사용하는 프로토콜 (https)
        2. Host(Domain name) : 요청 받는 웹 서버 이름. IP 주소로 사용할 수 있음
        3. Port : 웹 서버 상의 리소스가 접근하는 기술적인 문
        4. Path : 웹 서버 상의 리소스 경로
        5. Query(Identifier) : Query String Parameters. 웹 서버에 제공되는 추가적 매개 변수로 &로 구분되는 key=value목록
        6. Frament : 자원 안에서 북마크의 한 종류

### HTTP request methods
- 자원에 대한 행위, 수행하길 원하는 행동
- GET, POST, PUT, DELETE 등

### HTTP request status codes
- 특정 HTTP 요청이 성공적으로 완료되었는지
- 응답은 5개 그룹으로 나뉘어짐
    1. Informational responses (1XX)
    2. Successful responses (2XX)
    3. Redirection messages (3XX)
    4. Client error response (4XX)
    5. Server error response (5XX)
