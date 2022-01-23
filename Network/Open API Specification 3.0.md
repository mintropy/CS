# Open API 3.0 (OAS, Open API Specification)

> The OpenAPI Specification (OAS) defines a standard, language-agnostic interface to RESTful APIs which allows both humans and computers to discover and understand the capabilities of the service without access to source code, documentation, or through network traffic inspection. When properly defined, a consumer can understand and interact with the remote service with a minimal amount of implementation logic.

>OAS는 표준을 정의하며, 프로그래밍 언어에 구애받지 않는 RESTful API의 인터페이스이다. 이는 사람과 컴퓨터가 소스코드나 문서에 접근하지 않고도 (또는 네트워크 트래픽(패킷) 분석 통해) 해당 서비스(애플리케이션)의 기능을 찾거나 이해할 수 있게 해준다. 적절하게 OAS를 정의했다면 소비자들(Client Side)은 최소한의 작성분량(implementation logic에 대한 의역)으로도 서버를 이해하고 소통할 수 있다.

- [drf-spectaular](../Django/drf-spectacular.md)

## Why OpenAPI
- OpenAPI, REST API를 동시에 구현할 수 있음
    - OpenAPI를 통하여 더욱 쉬운 REST API 문서 구현 가능
- OAS : REST API 인터페이스 설명 방법 정의
    - 어떻게? OPEN API 정의
    - 무엇으로? YAML or JSON
    - 무엇을? 서버가 할 수 있는 작업
- OAS의 이점은 무엇이기에 사용해야하는가?
    - 표준화된 양식이므로, 사람과 기계모두 이해할 수 있음
        - REST API 리소스, 엔드 포인트, 작업, 권한 등 설명할 수 있음
    - 안내
        - 누구나 API를 이해하고 사용할 수 있음
    - OpenAPI로 REST API 확장할 수 있음
        - API 유효성 검사, API문서 생성
        - SDK생성기
- 그러면 어떤 정보가 있을까?
    - 기본 REST API 정보 : url, 설명 등
    - REST API 요청 : HTTP 메서드, 패스 등
    - REST API 응답 : HTTP status, 반환 데이터
    - example

## about OAS 3.0

![OAS 2.0 and 3.0](https://www.openapis.org/wp-content/uploads/sites/3/2017/03/image00-1-768x539.png)

- OAS 2.0에서 3.0으로의 큰 변화는 확장성과 간결성

```YAML
openapi: 3.0.0
info:
    title: Sample API
    description: Optional multiline or single-line description in [CommonMark](http://commonmark.org/help/) or HTML.
    version: 0.1.9
servers:
    - url: http://api.example.com/v1
    description: Optional server description, e.g. Main (production) server
    - url: http://staging-api.example.com
    description: Optional server description, e.g. Internal staging server for testing
paths:
    /users:
    get:
        summary: Returns a list of users.
        description: Optional extended description in CommonMark or HTML.
        responses:
        '200':    # status code
            description: A JSON array of user names
            content:
            application/json:
                schema: 
                type: array
                items: 
                    type: string
```

- YAML 기본 구조

# 참조
- https://techblog.yogiyo.co.kr/django-rest-framework-api-document-generator-feat-drf-spectacular-585fcabec404
- https://www.youtube.com/watch?v=pRS9LRBgjYg
- https://swagger.io/docs/specification/basic-structure/
