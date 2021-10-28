### Django Database CRUD
#### 1. 테이블 생성 : models.py를 통하여 테이블 생성
```python
# /models.py
class Article(models.Model):
    title = models.CharField(max_length=10)
    content = models.TextField()
```
- 각 모델은 django.db.models.Model 클래스를 상속받아 서브 클래스로 표현
- 각 필드는 models의 다양한 Field로 나타냄
  - [Django Model Fields](https://docs.djangoproject.com/en/3.2/ref/models/fields/)
- 각 모델 작성 후 migration 필요함
```bash
$ python manage.py makemigrations
$ python manage.py migrate
$ python manage.py sqlmigrate
$ python manage.py showmigartions
```

#### 2. DB API
Django가 제공하는 ORM을 활용, DB를 쉽게 조작하는 방법
기본 구조는 ClassName.Manager.QuerySetAPI 형식

#### 3. READ
```python
# QuerySet 복사본 반환
Article.objects.all()
# 특정 매개변수와 일치하는 객체 반환
Article.objects.get(pk=100)
# 특정 조건을 만족하는 새 QuerySet 반환
Article.objects.filter(title='title')
```

#### 4. CREATE
```python
# 인스턴스 생성 후 저장
article = Article()
article.title = 'title'
article.content = 'content'
article.save()
# 초기 값을 추가하여 인스턴스 생성 후 저장
article = Article(title='title', content='content')
article.save()
# QuerySetAPI create() 활용
Article.objects.create(title='title', content='content')
```

#### 5. UPDATE
```python
# 조회 >> 수정 >> 저장
article = Aritlcle.objects.get(pk=1)
article.title= 'new title'
article.save()
```

#### 6. DELETE
```python
article = Article.objects.get(pk=1)
article.delete()
```