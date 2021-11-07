### DOM(Documnet Object Model)
- HTML, XML과 같은 문서를 다루는 문서 프로그래밍 인터페이스
- 문서를 구조화하고 구조화된 구성 요서를 하나의 객체로 취급하여 다루는 논리적 트리 모델
- 문서가 구조화되어 있고, 각 요소를 객체로 취급
    - window : DOM을 표현하는 창으로 최상위 객체
    - document : 페이지 컨텐츠의 Entry Point역할, 다양한 태그 포함

- BOM(Browser Object Model) : JS가 브라우저와 소통하기 위한 모델

### DOM 조작
- DOM 조작은 선택 - 변경을 순서대로 작업

1. DOM 선택
```JavaScript
Document.querySelector(selector)
Document.querySelectorAll(selector)
```
- querySelector 는 선택자와 일치하는 요소 하나를 선택
    - 여러 개 존재하면 첫 번째, 없다면 null
- querySelectorAll 는 선택자와 일치하는 모든 요소 선택
    - 해당하는 NodeList를 제공하고, index로 접근 가능
    - Static Collection으로 실시간 반영되지 않음
- getElementByID, getElementByTagName, getElementByClassName으로 특정 id, 태그 이름, 클래스 이름에 따라 선택할 수 있음
- Collection
    - Live Collection : 문서가 바뀔 때 실시간으로 업데이트
    - Static Collection(non live) : DOM이 변경되어도 변경되지 않음

2. DOM 변경
```JavaScript
Documnet.createElement(tagName)
```
- 태그명에 해당하는 새로운 HTML 생성 / 반환
```JavaScript
Element.append()
Node.appendChild()
```
- append는 하나 또는 여러개의 요소를 추가, 반환값이 없음
- appendChild는 하나의 요소만 추가하고, 반환
- append는 DOMString 객체를 추가할 수 있지만, appendChild는 Node 객체만 허용
```JavaScript
Node.innerText
Element.innerHTML
```
- innerText는 해당 요소 내부의 텍스트를 변경
- innerHTML은 요소 내 포함된 HTML마크업을 반환
    - XSS공격에 취약하므로, 입력을 받는 부분에 사용 금지
```JavaScript
childNode.remove()
Node.removeChild()
```
- remove로 해당 노드 제거
- removeChild로 자식 노드를 제거하고 반환
```JavaScript
Element.setAttribute(name, value)
Element.getAttribute(attributeNmae)
```
- setAttribute 로 지정된 요소의 값 성정
- getAttribute 로 해당 요소의 값을 문자열로 반환

### Event
- 네트워크, 사용자 활동 등 사건 발생을 알리는 객체

##### [addEventListenr](https://developer.mozilla.org/ko/docs/Web/API/EventTarget/addEventListener)
```JavaScript
target.addEventListenr(type, listener)
```
- addEventListenr를 통하여 이벤트가 지정될 때마다 호출할 함수 설정
- type에는 반을 할 이벤트 유형, listener
```JavaScript
const btn = document.querySelector('button')
btn.addEventListener('click', function (event) {
    console.log(event)
})
```

##### [preventDefault](https://developer.mozilla.org/ko/docs/Web/API/Event/preventDefault)
- 어떤 이벤트가 동작하지 않도록 함
