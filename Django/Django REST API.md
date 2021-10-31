### Django REST API
- JSON응답은 다양한 방법으로 가능함
### JsonResponse
- django.http.response.JsonResponse로 JSON객체 반환
### Django Serializer
- Serializer : Queryset 및 Model Instance등을 JSON, XML등 유형으로 쉽게 변환
- django.core.serializers로 JSON객체 반환
### Django REST Framework
- Django REST Framework(DRF) 라이브러리를 활용하여 JSON응답 가능
- 각 app 폴더에 serializers.py 생성 후 모델에 맞추어 필드를 생성해주는 ModelSerializer 사용
  - rest_framework.serializers.ModelSerializer
