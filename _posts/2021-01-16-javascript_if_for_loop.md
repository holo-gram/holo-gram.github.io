---
title: "Jvascript operator, if, for loop"
categories:
  - Github blog
tags:
  - Jvascript
  - operator
  - if
  - for
---

## Jvascript operator, if, for loop

##### 1. Increment and decrement operators
```js
let counter = 2;
const preIncrement = ++counter; 
// counter에 1을 먼저 더한다음 preIncrement에 값을 할당한다.
// counter = counter + 1;
// preIncrement = counter;

const postIncrement = counter++;
//먼저 변수counter의 값을 postIncrement에 할당한 다음에 그 뒤에 counter값을 1증가 시킨다.
// postIncrement = counter;
// counter = counter + 1;
```


##### 2. Logical operators: || (or), && (and), ! (not)
```js
const value1 = true;
const value2 = 4 < 2;

// || (or), finds the first truthy value 
// 3개중에 하나라도 true면 true
console.log(`or: ${value1 || value2 || check()}`);
// or 연산자는 처음부터 true가 나오면 true!!
// 순서주의 (익스프레션, heavy한 오퍼레이션, 함수 호출하는것을 제일 뒤에 배치하는것이 효율적인 코드!)

// && (and), finds the first falsy value 
// 3개다 true여야 true!
console.log(`and: ${value1 && value2 && check()}`);
// often used to compress long if-statement
// nullableObject && nullableObject.something
if (nullableObject != null) {
    nullableObject.something;
}

// ! (not) 값을 반대로 바꿔줌
console.log(!value1);
```

##### 3. Equality
```js
const stringFive = '5';
const numberFive = 5;

// == loose equality, with type conversion
console.log(stringFive == numberFive);
console.log(stringFive != numberFive);

// === strict equality, no type conversion 타입이 다르면 다름
console.log(stringFive === numberFive);
console.log(stringFive !== numberFive);

// object equality by reference
const ellie1 = { name: 'ellie' };
const ellie2 = { name: 'ellie' };
const ellie3 = ellie1;
console.log(ellie1 == ellie2);
console.log(ellie1 === ellie2);
console.log(ellie1 === ellie3);

// equality - puzzler
console.log(0 == false); // true
console.log(0 === false); // false 0은 boolean타입이 아니므로
console.log('' == false); // true
console.log('' === false); // false ''문자열은 boolean타입이 아니므로
console.log(null == undefined); // true
console.log(null === undefined); // false 
```

##### 4. Conditional operators: if
```js
// if, else if, else
const name = 'df';
if (name === 'ellie') {
  console.log('Welcome, Ellie!');
} else if (name === 'coder') {
  console.log('You are amazing coder');
} else {
  console.log('unkwnon');
}
```

##### 5. Ternary operator: ?
```js
// condition ? value1 : value2;
console.log(name === 'ellie' ? 'yes' : 'no'); 
// true면 yes false면 no
// 값을 할당하거나 간단하게 출력시 좋음
```

##### 6. Switch statement
```js
// use for multiple if checks
// use for enum-like value check
// use for multiple type checks in TS
// 여러개를 반복 하거나 정해져 있는 타입을 검사할때 가독성이 좋음
const browser = 'IE';
switch (browser) {
  case 'IE':
    console.log('go away!');
    break;
  case 'Chrome':
  case 'Firefox':
    console.log('love you!');
    break;
  default:
    console.log('same all!');
    break;
}
```

##### 7. Loops
```js
// while loop, while the condition is truthy, 
// body code is executed.
let i = 3;
while (i > 0) {
  console.log(`while: ${i}`);
  i--;
}

// do while loop, body code is executed first, {}블럭을 실행 후 조건이 맞는지 안맞는지 검사
// then check the condition. 
do {
  console.log(`do while: ${i}`);
  i--;
} while (i > 0);
// 조건문이 맞을때만 블럭을 실행하고 싶으면 while, 
// 블럭을 먼저 실행하고 싶다면 do while


// for loop, for(begin; condition; step)
for (i = 3; i > 0; i--) {
  console.log(`for: ${i}`);
}

for (let i = 3; i > 0; i = i - 2) {
  // inline variable declaration
  console.log(`inline variable for: ${i}`);
}
```

> ## 출처 : 드림코딩 엘리
<!-- Link -->
Click [Here](https://youtu.be/YBjufjBaxHo)
