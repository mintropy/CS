### Vuex
- 상태 관리 패턴 + 라이브러리
- 상태(state)를 전역 저장소로 관리할 수 있도록 지원하는 라이브러리
    - 애플리케이션의 모든 컴포넌트에 대한 중앙 집중식 저장소 역할

- 단방향 흐름에 의한 상태관리는
    - 부모-자식 간 관계가 단순하거나 depth가 깊지 않으면 문제되지 않음
    - 규모가 커졌을 때 상태 관리가 어려워짐
- Vuex로 한 곳에 모아 관리할 수 있음

### Vuex 핵심 컨셉
- State, Mutations, Actions, Getters

1. State

- 중앙에서 관리하는 모든 상태 정보
- single state tree를 사용
- 모든 애플리케이션 상태를 포함하는 원본 소스 역할
- 각 애플리케이션마다 하나의 저장소만 갖게 됨
- State가 변화하면 해당 state를 공유하는 DOM은 알아서 렌더링

2. Mutations

- 실제로 state를 변경하는 유일한 방법
- handler 함수는 동기적이여야 함
    - 비동기적 로직은 state가 변화하는 시점이 의도한 것과 달라질 수 있음
- 첫 번째 인자로 state를 받음
- Actions에서 commit() 메서드로 호출

3. Actions

- state를 변경하는 대신 mutaions를 commit()메서드로 호출-실행
- 비동기 작업을 포함하여 API통싱 등 가능
- 컴포넌트에서 dispatch() 메서드로 호출
- state를 조작할 수 있지만, 명확한 역할 분담을 위해 state조작은 mutations를 통해서만 해야함

4. Getters

- state를 변경하지 않고 활용하여 계산 (computed와 유사)

### How to Vuex project
- Vue 프로젝트 생성 후 vuex 플러그인 추가

```bash
vue add vuex
```

- 추가적으로 store 디렉토리 생성 : 모든 파일을 모아두는 저장수
    - 내부에 index.js 생성 : Vuex 중요 컨셉들이 작성되는 곳

### Component Binding Helper
- 논리적인 코드 자체가 변하는 것이 아니라 쉽게 사용할 수 있도록 함
- mapState, mapGetters, mapActions, mapMutations

### Local Storage
- 로컬 저장소에 자동으로 저장해주는 라이브러리

```bash
npm i vuex-persistedstate
```
