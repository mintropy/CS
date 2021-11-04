### [Vue.js](https://kr.vuejs.org/v2/guide/)
사용자 인터페이스를 만들기 위한 진보적인 프레임워크
DOM과 Data가 연결되어 있으면, DOM을 직접 조작하지 않고 Data변경을 처리할 수 있게 함


### [Concepts of Vue.js](https://ko.wikipedia.org/wiki/모델-뷰-뷰모델)
- MVVM Pattern
    - Model : JavaScript Object, data로 사용 되고 이 값이 바뀌면 DOM이 반응
    - View : DOM, data의 변화에 따라 바뀌는 대상
    - ViewModel : 모든 Vue Instace, Data와 DOM에 관련된 모든 일 처리


### [Vue 인스턴스](https://kr.vuejs.org/v2/guide/instance.html)
모든 Vue앱은 Vue 함수로 새 Vue 인스턴스를 만드는 것으로 시작
```JavaScript
const app = new Vue ({
  // 옵션
})
```
1. el
Vue 인스턴스에 연결할 DOM 엘리먼트
CSS 선택자 문자열 / HTML Element로 작성
new로 생성할 때만 사용
```JavaScript
const app = new Vue ({
  el: '#app',
})
```
2. data
Vue 인스턴스의 데이터 객체, 상태 데이터 정의
Vue template에서 interpolation을 통해 접근 가능
v-bind, v-on 등 directive에서 사용 가능
```JavaScript
const app = new Vue ({
  el: '#app',
  data: {
    message: 'Hello',
  },
})
```
3. methods
Vue 인스턴스에 추가할 메서드
Vue template에서 interpolation을 통해 접근 가능
v-bind, v-on 등 directive에서 사용 가능
- this 키워드를 통하여 Vue 인스턴스 내 데이터, 메서드 등 접근 가능
```JavaScript
const app = new Vue ({
  el: '#app',
  data: {
    message: 'Hello',
  },
  methods: {
    greeting: function () {
      console.log('hello')
      console.log(this.message)
    }
  },
})
```


### [Template Syntax](https://kr.vuejs.org/v2/guide/syntax.html)
렌더링 된 DOM을 기본 Vue 인스턴스의 데이터에 선언적으로 바인딩 할 수 있는 HTML 기반 템플릿 구문
1. 보간법(Interpolation)
```html
<!-- Text -->
<span>{{ message }}</span>
<!-- Raw HTML -->
<span v-html="rawHTML"></span>
<!-- Attributes -->
<span v-bind:id="dynamicId"></span>
<!-- JS 표현식 -->
{{ number + 1}}
{{ ok ? 'YES' : 'NO' }}
```

2. 디렉티브(Directive)
v- 접두사가 있는 특수 속성으로, 속성 값은 단일 JavaScript표현식
- 전달인자(arguments) : ':', 콜론을 통해 전달인자를 받을 수 있음
- 수식어(modifiers) : '.'으로 표현되는 특수 접미사
- [Vue.js Directive](Vue.js%20Directive.md)