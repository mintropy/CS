# [drf-spectacular @extend_schema](https://drf-spectacular.readthedocs.io/en/latest/drf_spectacular.html#drf_spectacular.utils.extend_schema)

- drf_spectacular.utils.extend_schema
- view에서 swagger의 스키마를 더욱 정확하게 정의할 수 있는 데코레이터 함수
- 기본적으로 많은 부분이 자동적으로 생성되지만, 수동적으로 생성해줄 수 있음
- parameters, responses, request, auth, description, summary등의 정보 입력 가능



# @extend_schema 작성

## reponses

- 기존 serializer의 내용을 대체하고, 다양한 방법으로 입력할 수 있음
- 입력
  - Serializer 클래스
  - Serializer 인스턴스
  - OpenApiResponse
  - PolymorphicProxySerializer
  - dict로 status code를 키로, 위의 값중 하나를 값으로 가짐
  - dict로 (status_code, media_type)을 키로, 위의 값중 하나를 값으로 가짐

#### OpenApiResponse

- response를 생성하는 방법
- parameter로 response, description, examples를 받음
- response는 Serializer, OpenApiType 등으로 받을 수 있음
  - 기존 Serializer를 활용할 수 있음
  - Serializer를 활용할 때, inline_serializer를 활용할 수 있음
    - 이 때, OpenApiResponse내에서 examples이 작동하지 않아서, 예시가 필요한경우 따로 작성해야함
- description으로 해당 status code에 대한 설명을 추가할 수 있음
- examples는 OpenApiExample로 이루어진 리스트로 표현 가능

#### inline_serializer

- extend_schema내부에서 serializer 클래스 표현이 필요할 때, 일회용 serializer를 생성 및 활용할 수 있음
- name과 fields로 이루어짐

#### example

```python
@extend_schema(
	responses={
        200: OpenApiResponse(
        	response=UserDetailSerializer,
            description='User information',
            OpenApiExample(...)
        ),
        401: OpenApiResponse(
        	response=inline_serializer(
            	name='error',
                fields={
                    'error': serializers.CharField(),
                }
            ),
            description='Unauthorized',
        )
    }
)
```

## request

- 기존 serializer의 내용을 대체하고, 다양한 방법으로 입력할 수 있음
- response와 같은 방식으로 작성할 수 있음

##  description

- docstring으로 작성된 설명을 대신함

## summary

- swagger 페이지에서 API url다음에 요약으로 보임
- redoc페이지에서는 descritption 위에 보임

## tags

- 기본 tag(=app 기준)을 대체함

## methods

- method를 작성할 수 있지만, 기본적으로 APIView에서 제공하는 함수(get, post ...)을 사용할때는 상관 없음

## versions

- API버전을 구분하여 실행될 수 있음

## examples 

- response와 request에 대한 예시를 작성할 수 있음

#### OpenApiExamples

- name, value, status_codes 등을 가지고, request_only, response_only를 활용해서 request, response에 대한 예시 작성할 수 있음
