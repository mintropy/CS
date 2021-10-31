### Django Form Class
- form의 유효성 검사 도구 중 하나로, 공격, 데이터 손상 등 을 방지하는 수단
- 렌더링을 위한 데이터 준비 및 재구성, HTML forms 생성, 클라이언트로부터 받은 데이터 수신 및 처리

### [Form Class](https://docs.djangoproject.com/en/3.2/topics/forms/)
- form내부의 field, field 배치, 디스플레이 widget, label, 초기값, 유효하지 않은 filed에 관련한 에러 메세지 등 결정
```python
from django import forms
class ArticleFrom(forms.Form):
    title = forms.CharField(max_length=10)
    content = forms.CharField()
```
- html에서 form을 출력하는 3가지 옵션 존재
  - as_p(), al_ul(), as_table()
#### [widget](https://docs.djangoproject.com/en/3.2/ref/forms/widgets/)
- HTML 렌더링을 처리
```python
from django import forms
class ArticleFrom(forms.Form):
    title = forms.CharField(max_length=10)
    content = forms.CharField(widget=forms.Textarea)
```

### [MddelForm](https://docs.djangoproject.com/en/3.2/topics/forms/modelforms/)
- 기존 Model을 활용할 때, Form으로 생성하면 중복 행위 발생
- Model을 그대로 사용할 수 있는 ModelFrom
```python
from django import forms
from .modles import Model
class FormUseModelForm(forms.ModelForm):
    class Meta:
        model = Model
        fields = '__all__'
```
- Meta 클래스를 선언하고, 사용할 모델과 사용할 필드를 정의