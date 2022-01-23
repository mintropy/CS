## [Strawberry](https://strawberry.rocks/)
- GraphQL library for Python 3, inspired by dataclasses
    - [Python Data Classes](https://realpython.com/python-data-classes/)
    - [Python Type Hint](https://docs.python.org/3/library/typing.html)

## Getting Started with Django
- GraphQLView는 다섯가지 옵션이 있음

    1. schema : strawberry.Schema에 의해 생성된 스키마
    2. graphiql : 옵션, True, GraphiQL 인터페이스를 허용할것인지
    3. subscriptions_enabled : 옵션, False, enabling subscriptions in GraphiQL interface
    4. json_encoder : 옵션, DjangoJSONEncoder, 데이터의 serializer
    5. json_dumps_params : 옵션, None, JSON을 어떻게 생성할지

