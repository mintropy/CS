### Admin Site
- admin 생성
```
$ python manage.py createsuperuser
```
- 각 앱의 admin.py에서 각 앱의 관리 사항 등록 가능
```python
# Model 이라는 이름의 모델을 등록
from .models import Model
admin.site.register(Model)
```
- 각 앱에서 표시하 항목 조정 가능
```python
from .models import Model
class ModelDisplayAdmin(admin.ModelAdmin):
    list_display = ('pk', 'title', ...)
admin.site.register(Model)
```