### AJAX(Asynchronous JavaScript And XML, 비동기식 JS와 XML)
- 서버와 통신하기 위해 XMLHttpRequest 객체 활용
- JSON, XML, HTML, 텍스트 등 다양한 포맷을 주고 받을 수 있음
- 페이지 전체를 새로고침 하지 않고서도 수행되는 비동기성

##### XMLHttpRequest 객체
- 서버와 상호작용하기 위해 사용되며, 페이저 전체를 새로고침 없이 데이터를 받아올 수 있음
```JavaScript
const request = new XMLHttpRequest()
const URL = 'URL'

request.open('GET', URL)
request.send()

const response = request.response
console.log(response)
```
- 코드 작성 흐름은 틀리지 않았지만, 실제 실행하면 아무런 데이터가 출력되지 않음
- JS는 single thread 언어라서 한번에 하나의 작업만 수행 할 수 있음
    - 작업을 Call Stack에 추가
    - 바로 처리하지 못하면 Web API에서 처리
    - 처리된 이벤트를 순서대로 Task Queue에 추가
    - Call Stack이 비어있으면 Task Qeueu의 가장 앞의 이벤트를 보냄
- 순차적 비동기 처리를 하기위한 두가지 방법 존재
    - Async callbacks : addEventListener의 두번째 인자
    - promise-style

### Promise object
- 비동기 작업의 최종 완료 또는 실패를 나타내는 객체
- .then() : 성공에 대한 약속
- .catch() : 실패에 대한 약속
- .finally() : 무조건 실행되는 부분

### Axios
- Promise based HTTP client for the browser and Node.js
```JavaScript
axios.get('URL')
  .then(...)
  .then(...)
  .catch(...)
  .finally(...)
```
