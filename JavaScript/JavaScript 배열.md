### 배열
- 키와 속성을 담고 있는 객체
- 순서를 보장
- 0과 양의 정수 인덱스로 값 접근 가능
```JavaScript
const numbers = [1, 2, 3, 4, 5]

console.log(numbers[0])  // 1
console.log(numbers[3])  // 4
```

#### 메서드
1. length
```JavaScript
const numbers = [1, 2, 3, 4, 5]
console.log(numbers.length)  // 5
```

2. reverse
```JavaScript
const numbers = [1, 2, 3, 4, 5]
numbers.reverse()
console.log(numbers) // [5, 4, 3, 2, 1]
```

3. push / pop
```JavaScript
const numbers = [1, 2, 3, 4, 5]
// push : 가장 뒤에 추가
numbers.push(6)
console.log(numbers) // [1, 2, 3, 4, 5, 6]
// pop : 가장 뒤 요소 제거
numbers.pop()
console.log(numbers) // [1, 2, 3, 4, 5]
```

4. upshift / shift
```JavaScript
const numbers = [1, 2, 3, 4, 5]
numbers.upshift(6)
console.log(numbers) // [6, 1, 2, 3, 4, 5]
// pop : 가장 뒤 요소 제거
numbers.shift()
console.log(numbers) // [1, 2, 3, 4, 5]
```

5. includes
```JavaScript
const numbers = [1, 2, 3, 4, 5]

console.log(numbers.includes(1))  // true
console.log(numbers.includes(6))  // false
```

6. indexOf
```JavaScript
const numbers = [1, 2, 3, 4, 5]

console.log(numbers.indexOf(1))  // 0
console.log(numbers.indexOf(6))  // -1
```

7. join
```JavaScript
const numbers = [1, 2, 3, 4, 5]
let result

result = numbers.join()
console.log(result)  // 1,2,3,4,5
result = numbers.join('')
console.log(result)  // 12345
```

- 매서드 호출 시 인자로 callback함수를 받는 경우도 존재
    - callback 함수 : 어떤 함수 내부에서 실행될 목적으로 인자로 넘겨 받는 함수

8. forEach
```JavaScript
const fruits = ['apple', 'banana', 'mango']

fruits.forEach((fruit, index) => {
  console.log(fruit, index)
  // apple 0
  // banana 1
  // mango 2
})
```

9. map
```JavaScript
const numbers = [1, 2, 3, 4, 5]

const doubleNumbers = numbers.map((number) => {
  return number * 2
})
console.log(doubleNumbers)  // [2, 4, 6, 8, 10]
```

10. filter
```JavaScript
const numbers = [1, 2, 3, 4, 5]

const oddNumbers = numbers.map((number) => {
  return number % 2
})
console.log(doubleNumbers)  // [1, 3, 4]
```

11. reduce
```JavaScript
const numbers = [1, 2, 3, 4, 5]

const result = numbers.reduce((acc, num) => {
  return acc + num
})
console.log(result)  // 10
```

12. find
```JavaScript
const people = [
  { name: 'kim', ange: 42},
  { name: 'lee', ange: 12},
  { name: 'park', ange: 34},
]

const result = people.find((person) => {
  return person.name === 'kim'
})

console.log(person)  // { name: 'kim', ange: 42}
```

13. some
```JavaScript
const numbers = [2, 4, 6, 8]

const hasEvenNumber = numbers.some((num) => {
    return num % 2 === 0
})
console.log(hasEvenNumber)  // true

const hasOddNumber = numbers.some((num) => {
    return num % 2
})
console.log(hasOddNumber)  // true
```

14.  every
```JavaScript
const numbers = [2, 4, 6, 8]

const isAllEvenNumber = numbers.every((num) => {
    return num % 2 === 0
})
console.log(hasEvenNumber)  // true

const isAllOddNumber = numbers.every((num) => {
    return num % 2
})
console.log(hasOddNumber)  // true
```
