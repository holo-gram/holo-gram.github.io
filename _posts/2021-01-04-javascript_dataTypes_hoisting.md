---
title: "Jvascript 데이터타입, hoisting"
categories:
  - Github blog
tags:
  - data types
  - hoisting
---

## Jvascript 데이터타입, hoisting

##### 1. Variable(변수: 변경될 수 있는 값)
> let (added in ES6)

Global scope 
**어느곳에서나 접근이 가능** 
```js
let globalName = 'global name';
```
글로벌한 변수들은 어플리케이션이 실행되는 순간부터 끝날때까지 항상 메모리에 탑재되어있기 때문에 최소한으로 쓰는것이 좋다. 그러므로 가능하면 필요한 부분에서만 정의해서 쓰는게 좋다.


Block scope 
**Block 밖에서는 Block안의 내용들을 볼 수 없게된다.**
```js
{
  let name = 'ellie';
  console.log(name);
  name = 'hello';
  console.log(name);
  console.log(globalName); //{}안에서도 보이고
}

console.log(name); //Block 밖에서 접근하게 되면 아무값도 나오지 않는다.
console.log(globalName); //{}밖에서도 보인다.
```

##### 2. hoisting
어디에 선언했느냐에 상관없이 항상 제일위로 선언을 끌어올려주는것!

**var**
- var hoisting (move declaration from bottom to top) 
- has no block scope


##### 3. const
- 한번 할당하면 값이 절대 바뀌지 않는다.
- 값을 선언함과 동시에 바꿀수 없다.

favor immutable data type always for a few reasons
1. security
2. thread safety
3. reduce human mistakes


##### null 
**비어있는값을 지정해주는것**
```js
let nothing = null;
```

##### undefined
**선언은 되었지만 아무값도 지정되어있지 않은것**
```js
let x;
let x = undefined;
```


#### symbol
map이나 자료구조에서 고유한 식별자가 필요하거나 동시 다발적으로 우선순위를 주고싶을때 쓰여짐
```js
const symbol1 = Symbol('id');
const symbol2 = Symbol('id');
console.log(symbol1 === symbol2);
```
주어진 string에 상관없이 고유한 식별자를 만들때 사용


```js
const gSymbol1 = Symbol.for('id');
const gSymbol2 = Symbol.for('id');
console.log(gSymbol1 === gSymbol2); // true
```
주어진 string에 맞는 symbol을 만들때는 Symbol.for



```js
console.log(`value: ${symbol1}, type: ${typeof symbol1}`);
```
이렇게 하면 에러뜸!

```js
console.log(`value: ${symbol1.description}, type: ${typeof symbol1}`);
```
**.description**으로 string으로 변환하고 출력해야함!


> ## 출처 : 드림코딩 엘리
<!-- Link -->
Click [Here](https://youtu.be/OCCpGh4ujb8)
