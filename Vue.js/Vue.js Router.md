### Vue Router

- route에 컴포넌트를 매핑한 후, 어떤 주소에서 렌더링할 지 알려 줌
- SPA상에서 라우팅을 쉽게 할 수 있는 기능 제공

```bash
vue create my-router-app
vue add router
```

Vue Router로인해 다음과 같은 변화 생김

- App.vue 코드
- router/index.js 생성 : 라우트에 관련된 정보 및 설정
- views 디렉토리 생성

##### router-link

- <router-link> : 사용자 네비게이션을 가능하게 하는 컴포넌트
- 목표 경로는 'to'로 하는 prop로 지정
- router-link는 클릭 이벤트를 차단, 브라우저가 다시 로드 하지 않도록 함

##### History mode

- HTML Hisotry API를 사용, router 구현
- 브라우저의 히스토리는 남지만 실제 페이지는 이동하지 않는 기능 지원
- SPA단점 중 하나인 URL 변경되지 않는 부분의 해결 방법

1. Named Routes

- 이름을 가지는 라우트
- 명명된 경로로 이동하려면 객체를 vue-router 컴포넌트 요소인 prop에 전달

2. 프로그래밍 방식 네비게이션

- <router-link>를 사용, 선언적 탐색을 위한 a태그를 만드는 것 외에도, router의 인스턴스 메서드를 사용하여 프로그맹 방식으로 가능
  - 선언적 방식 : <router-link to="...">
  - 프로그래밍 방식 : router.push(...)
- Vue 인스턴스 내부에서 라우터 인스턴스에 $router로 접근가능
- 다른 URL로 이동하려면 this.$router.push 호출 가능

```vue
router.push('home')
router.push({ path: 'home'})
router.push({ name: 'user', params: { userId: '123' } })
router.push({ path: 'register', query: { plan: 'private' } })
```

3. Dynamic Route  Matching

- 동적 인자 절달
- 주어진 패턴을 가진 라우트를 동일한 컴포넌트에 매핑해야 하는 경우
- 동적 인자는 콜론으로 시작, 컴포넌트에서 this.$route.params로 사용가능
  - /user/:userName