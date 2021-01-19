---
title: "Jvascript function"
categories:
  - Github blog
tags:
  - function
---

## Jvascript function
1. fundamental building block in the program<br/>
**프로그램을 구성하는 빌딩 블록**
2. subprogram can be used multiple times<br/>
**subprogram 이라고도 불리며 여러번 재사용이 가능함**
3. performs a task or calculates a value<br/>
**한가지의 task나 어떤 값을 계산하기 위해 쓰여짐**

##### 1. Jvascript에서 function을 정의하는 방법
**function name(param1, param2) { body... return; }**<br/>
**one function === one thing**<br/>
**naming: doSomething, command, verb** 이름은 동사형태로!

🍎function is object in JS🍎
1. **변수 할당 가능**
2. **파라미터로 전달**
3. **함수를 리턴**

##### 2. Parameters
1. premitive parameters: passed by value
- 메모리에 value가 그대로 저장되어 있기 때문에 그대로 전달 됨.

2. object parameters: passed by reference
- 메모리에 레퍼런스가 저장됨, 그래서 레퍼런스가 전달 됨.

##### 3. Default parameters (added in ES6)
```js
function showMessage(message, from = 'unknown') {
  console.log(`${message} by ${from}`);
}
showMessage('Hi!');
```

##### 4. Rest parameters (added in ES6)
```js
function printAll(...args) {
  for (let i = 0; i < args.length; i++) {
    console.log(args[i]);
  }

  for (const arg of args) {
    console.log(arg);
  }

  args.forEach((arg) => console.log(arg));
}
printAll('dream', 'coding', 'ellie');
```

##### 5. Local scope
```js
let globalMessage = 'global'; // global variable 전역변수
function printMessage() {
  let message = 'hello';
  console.log(message); 
  // local variable 지역변수
  // { block안에서 변수선언 / 안에서만 접근 가능 / 안에서는 밖을 볼 수 있다.}
  console.log(globalMessage);
  function printAnother() {
    console.log(message);
    let childMessage = 'hello';
  }
  // console.log(childMessage); //error
}
printMessage();
```

##### 6. Return a value
```js
function sum(a, b) {
  return a + b;
}
const result = sum(1, 2); // 3
console.log(`sum: ${sum(1, 2)}`);
```
**return타입이 없는 함수들도 return undefined이 들어가 있는거랑 똑같다. 생략이 가능함**

##### 7. Early return, early exit
```js
// bad
function upgradeUser(user) {
  if (user.point > 10) {
    // long upgrade logic...
  }
}

// good
function upgradeUser(user) {
  if (user.point <= 10) {
    return;
  }
  // long upgrade logic...
}
```
{} blcok 안에서 로직을 많이 작성하면 가독성이 떨어진다. 이런경우 에는
if와 else를 번갈아 쓰는것보다 조건이 맞지 않을때는 빨리 리턴을 해서
함수를 종료하고, 조건이 맞을때만 그다음에 필요한 로직들을 쭉 실행 하는것이 더 좋다!

즉, 코드 작성시 조건이 맞지 않는 경우, 값이 undefined인 경우, 값이 -1인경우에는
빨리 return을 하고 필요한 로직들은 그 뒤에 작성하는것이 더 좋음!


- First-class function
- functions are treated like any other variable
- can be assigned as a value to variable
- can be passed as an argument to other functions.
- can be returned by another function

##### 1. Function expression
🍑 a function declaration can be called earlier than it is defiend. (hoisted)<br/>
🍑 a function expression is created when the execution reaches it.

```js
const print = function () {
  // anonymous function
  console.log('print');
};
print();
const printAgain = print;
printAgain();
const sumAgain = sum;
console.log(sumAgain(1, 3));
```

##### 2. Callback function using function expression
```js
function randomQuiz(answer, printYes, printNo) {
  if (answer === 'love you') {
    printYes();
  } else {
    printNo();
  }
}
// anonymous function
const printYes = function () {
  console.log('yes!');
};

// named function
// better debugging in debugger's stack traces
// recursions
const printNo = function print() {
  console.log('no!');
};
randomQuiz('wrong', printYes, printNo);
randomQuiz('love you', printYes, printNo);
```
##### 3. Arrow function
```js
// always anonymous
// const simplePrint = function () {
//   console.log('simplePrint!');
// };

const simplePrint = () => console.log('simplePrint!');
const add = (a, b) => a + b;
const simpleMultiply = (a, b) => {
  // do something more
  return a * b;
};
```
함수를 간결하게 만들어줌!


##### 4. IIFE: Immediately Invoked Function Expression<br/>(즉시실행함수)
```js
(function hello() {
  console.log('IIFE');
})();
```
**자바스크립트에서 함수를 바로 실행하고 싶을때 사용<br/>(바로 함수 호출)**


> ## 출처 : 드림코딩 엘리
<!-- Link -->
Click [Here](https://youtu.be/e_lU39U-5bQ)
