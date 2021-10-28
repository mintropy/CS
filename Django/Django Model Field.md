### [Django Model Field](https://docs.djangoproject.com/en/3.2/ref/models/fields/)
- CharField(max_length=None, **options)
  - 길이 제한 있는 문자열 넣을 때 사용
- DateTimeField(auto_now=False, auto_now_add=False, **options)
  - auto_now_add : 최초 생성
  - auto_now : 수정
- TextField(**options)
  - 글자 수가 많을 때 사용