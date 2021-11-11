### 요약
- Vue Cli를 사용하기 위해 설치 (npm install -g @vue/cli)
- 각 vue 파일을 하나의 component로 활용, 각 vue 파인은 HTML, script, css영역으로 구분
- 데이터는 props를 통해 아래로, emit event를 통하여 위로 이벤트를 알림
    - 자식 컴포넌트에 보내기 위해 HTML부분에서 자식이름 태그로 데이터 선언
    - 자식 컴포넌트에서 props를 통하여 명시적으로 선언후 사용
    - 부모에게 이벤트를 알릴 때 this.$emit()메서드를 활용해서 알릴 수 있음
    - 부모에서 v-on을 통하여 청취 후 데이터 읽을 수 있음

### SFC

컴포넌트 : 기본 HTML 엘리먼트 확장하여 재사용에 가능한 코드를 캡슐화 하는데 도움을 줌. 유지보수뿐만 아니라 재사용성에서도 강력한 기능 제공

- SFC (Single File Component)

Vue의 컴포넌트 기반 개발 핵심 특징

하나의 컴포넌트는 .vue확장자를 가진 하나의 파일 안에서 작성되는 결과물로, HTML, CSS, JS 코드를 하나의 파일에서 관리

### CLI

- Vue.js 개발을 위한 표준 도구
- Node.js : JS를 브라우저가 아닌 환경에서 구동할 수 있도록 하는 런타임 환경
- NPM (Node Package Manager) : JS 언어를 위한 패키지 관리자

```bash
npm install -g @vue/cli
vue create my-frist-app
vue run serve
```

Vue 프로젝트에는 다양한 파일이 있음

- Babel : JS compiler
  - 최신 코드를 구 버전으로 옮기는 번역기
- Webpack : static module bundler
  - 모듈 간 의존성 해결

전반적인 구조는 다음과 같음

- node_modules : node.js환경의 여러 의존성 모듈
- public/index.html : Vue앱의 뼈대가 되는 파일로, 실제 제공되는 당일 html 파일
- src/assets : webpack에 의해 빌드 된 정적 파일
- src/components : 하위 컴포넌트 위치
- src/App.vue : 최상위 컴포넌트
- src/main.js : webpack이 빌드를 시작할 때 가장 먼저 불러오는 entry point
- babel.config.js : babel 관련 설정
- package.json : 프로젝트 종속성 목록과 지원되는 브라우저에 대한 구성 옵션
- package-lock.json : 개발 및 배포 환경에서 정확히 동일한 종속성을 설치하도록 보장

### Props & Emit

- props는 아래로, events는 위로
- 부모가 자식으로 데이터를 전달하고, 자식은 부모에게 이벤트 발생을 알림
- 자식 컴포넌트는 부모를 직접 참조하지 못하므로 선언해줘야 함

```vue
<template>
	<div id="app">
        <about my-message="This is prop data"></about>
    </div>
</template>
```

- prop-data-name="value" 와 같은 형태로 작성

```vue
<template>
	<div id="app">
        <h2>{{ myMessage }}</h2>
    </div>
</template>

<script>
export default {
    name: 'About',
    props: {
        myMessage: String,
    }
}
</script>
```

- 수신한 prop 데이터를 명시적으로 선언 후 사용

```vue
<template>
	<div id="app">
        <about 
           my-message="This is prop data"
           :parent-data="parentData"
		>
    	</about>
    </div>
</template>

<script>
export default {
    name: 'App',
    components: {
        About
    },
    data: function () {
        return {
            parentData: 'Parent Data by v-bing'
        }
    }
}
</script>
```

- v-bind directive를 사용해 props를 동적으로 할당할 수 있음

- data는 무조건 함수로 작성해야 함

```vue
<script>
export default {
    name: 'About',
    data: function () {
        return {
            parentData: 'Parent Data by v-bing'
        }
    },
    props: {
        myMessage: String,
        parentData: String,
    },
    methods: {
        childInputChange: function () {
            this.$emit('child-input-change', this.childInputData)
        }
    }
}
</script>
```

- $emit으로 이벤트 발생, 부모 컴포넌트에 알릴 수 있음
- 부모 컴포넌트는 자식 컴포넌트가 사용되는 템플릿에서 v-on을 사용하여 자식 컴포넌트가 보낸 이벤트 청취