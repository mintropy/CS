### [조건문](https://developer.mozilla.org/ko/docs/Learn/JavaScript/Building_blocks/conditionals)
조건문은 if문과 switch문으로 구성할 수 있음

1. if문
```JavaScript
if (조건1) {
  조건1이 참일 때 실행할 코드
} else if (조건2) {
  조건2가 참일 때 실행할 코드
} else {
  모든 조건이 거짓일 때 실행할 코드
}
```

각 조건에 대해 비교 연산자를 사용할 수 있음
```
===, !== : 두개의 값이 같거나 다른지
>, < : 한 값이 다른 값보다 더 크거나 작은지
>=, <= : 한 값이 다른 값보다 더 크거나 같고 또는 작거나 같은지
```

각 조건에 대한  논리 연산자를 사용할 수 있음
```
&& : AND, || : OR, !: NOT
```

2. switch문
```JavaScript
switch (expression) {
  case choice1: {
    code 1
    [break]
  }
  case chose2: {
    code 2
    [break]
  }
  [default: {
    code
  ]}
}
```
expression의 값을 각각 case와 비교하여 코드를 실행
break와 default는 선택적으로 활용할수 있음
```
break : 해당 부분을 만나면 종료
default : 일치하는 항목이 없을 때 실행하는 기본값
```

### [반복문](https://developer.mozilla.org/ko/docs/Learn/JavaScript/Building_blocks/Looping_code)
while과 for로 구현할 수 있음

1. while
```JavaScript
while (종료 조건) {
  // 실행할 코드
}
```

2. do ... while
```JavaScript
// 초기화식
do {
  // 실행할 코드
} while (종료 조건)
```
while문과는 달리 적어도 한 번은 실행 됨

3. for
```JavaScript
for (초기화식; 종료조건; 증감식) {
  // 실행할 코드
}
```
추가적으로 break, continue로 for문 제어 가능

- for ... in : 객체의 속성을 순회할 때 사용
```JavaScript
for (variable in object) {
  // 실행할 코드
}
```
- for ... of : 반복 가능한 객체를 순회할 때 사용
```JavaScript
for (variable of iterables) {
  // 실행할 코드
}
```
- for ... in 과 for ... of는 둘 다 반복문으로 작동 가능
- 하지만 for ... in 은 반복 가능한 객체의 순서를 보장하지 않음
