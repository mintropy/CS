### [JavaScript 자료형](https://developer.mozilla.org/ko/docs/Web/JavaScript/Data_structures)

- 자바스크립트는 동적(dynamic) 언어. 변수의 타입을 미리 선언할 필요 없이, 같은 변수에 여러 타입을 저장 가능
- 자바스크립트 자료형은 Primitive(기본 타입, 원시 타입)과 Object(객체, Reference, 참조 타입)으로 나뉨

1. 기본 타입
6가지 자료형 : undefined, Boolean, Number, String, BigInt, Symbol
- Number : 정수, 실수 구분 없는 하나의 숫자 타입으로 부동 소수점 형식
- BigInt : 정수 끝에 n을 추가하거나 생성자를 호출하여 생성
- String : 텍스트 데이터로 16비트 유니코드로 이루어짐
- Undefined : 값을 할당하지 않은 변수
- Null : 값이 없음을 나타내는데, typeof를 통하여 확인하면 object로 표현됨
- Boolean : 논리적 참 또는 거짓을 나태는 요소
- Symbol : ECMAScript 6에서 추가됨. 유일하고 변경 불가능한 기본값

2. 객체
3가지 자료형 : Object(데이터 구조로 사용되는 모든 생성된 객체 인스턴스에 대한 데이터가 아닌 특수한 구조 유형), Function, Structural Root Primitive
