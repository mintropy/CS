### [함수](https://developer.mozilla.org/ko/docs/Learn/JavaScript/Building_blocks/Functions)
- function 타입
- 함수 선언식과 함수 표현식으로 정의 가능
- JS 함수는 [일급 객체](https://ko.wikipedia.org/wiki/입급_객체)
    - 변수에 할당 가능
    - 함수 매개변수로 전달 가능
    - 함수 반환 값으로 사용 가능

1. 함수 선언식
```JavaScript
function name(args) {
  // 코드
}
function add(numOne, numTwo) {
  return numOne + numTwo
}
```

2. 함수 표현식
```JavaScript
const myFunction = function (args) {
  // 코드
}
```
함수를 표현식 내에서 정의하는 방식으로, 익명 함수로 정의 가능

#### 화살표 함수(Arrow Function)
- 함수를 비교적 간결하게 정의
- function 키워드 생략 가능
- 함수 매개변수가 하나라면 () 생략 가능
- 함수 표현식이 하나라면 {}, return 생략 가능
```JavaScript
const arrow = function (name) {
  return `hello! ${name}`
}

const arrow = (name) => { return `hello! ${name}`}

const arrow = name => { return `hello! ${name}`}

const arrow = name => `hello! ${name}`
```


