# [drf-spectacular](https://drf-spectacular.readthedocs.io/en/latest/)
> Sane and flexible OpenAPI 3 schema generation for Django REST framework.

## drf-spectacular has 3 goals
1. Extract as much schema information from DRF as possible.
2. Provide flexibility to make the schema usable in the real world (not only toy examples).
3. Generate a schema that works well with the most popular client generators.

## Features
- Serializer를 컴포넌트처럼 모델링
- @extend_schema데코레이터로 APIView, Viwesers, fbv 그리고 @action을 커스터마이징 할 수 있음
- simple-JWT 등과도 호환이 됨

# @extend_schema
### queryset & serializer_class
- get_serializer_class()와 get_serializer()에 크게 의존하고, 설정할 수 있음
- DRF는 이를 지원하지 않아 자동적으로 선택함

### [@extend_schema](drf-spectacular%20extend_schema.md)
- @extend_schema데코레이터를 활용할 수 있음
- 여러 옵션이 있고, 자동으로 선택되지 않은 요소만 사용해도 됨
    - response와 같은 부분은 더욱 자세하게 설명을 붙여서 사용할 수 있음
    - inline_serializer를 활용하여 더 편리하게 정의 가능

### @extend_schema_field
- serializer field가 제대로 선택되지 않을 수 있기대문에, @extend_schema_field 데코레이터로 내용을 알려줄 수 있음

### @extend_schema_serializer
- serializer를 장식할 수 있음

### Extensions
- 다양한 extension으로 더욱 명확하게 구분할 수 있음
