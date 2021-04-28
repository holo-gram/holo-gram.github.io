---
title: "Javascript Array"
categories:
  - JAVASCRIPT
---

## Javascript Array
##### 1. Declaration
```js
const arr1 = new Array();
const arr2 = [1, 2];

```
##### 2. Index position
```js
  const fruits = ['🍎, 🍌'];
  console.log(fruits);
  console.log(fruits.length);
  console.log(fruits[0]);
  console.log(fruits[1]);
  console.log(fruits[fruits.length - 1]);
```

##### 3. Looping over an array
```js
// print all fruits
// a. for
for(let i = 0; i < fruits.length; i ++){
  console.log(fruits[i]);
}

//b. for of
for(let fruit of fruits) {
  console.log(fruit);
}


//c. forEach
// 전달한 callback 함수를 value하나 하나마다 호출
// thisArg? : any 파라미터를 전달해도 안해도 됨
// callback 함수에는 총 3가지의 인자가 들어옴
// 1. value (callback 함수 호출하는 value 즉 배열에 있는 값이 전달)
// 2. index (그 값이 들어있는 index)
// 3. array (전체적인 배열)

// fruits.forEach(function ( fruit, index, array ){ // array는 보통 생략함
//   console.log(fruit, index);
// });

// fruits.forEach(function ( fruit, index ){
//   console.log(fruit, index);
// });

// fruits.forEach( (fruit, index) => {
//   console.log(fruit, index);
// });

// fruits.forEach( (fruit, index) => console.log(fruit, index));

fruits.forEach((fruit) => console.log(fruit));
```

##### 4.  Addtion, deletion, copy
```js
// push: add an item to the end(배열 제일 뒤에 데이터 넣기)
fruits.push('🍓', '🍑');
console.log(fruits);

// pop: remove an item from the end(배열 제일 뒤에부터 데이터 지우기)
const poped = fruits.pop();
fruits.pop();
// fruits.pop(); 뒤에 한번 더 쓰면 데이터 한개 더 지워짐
console.log(fruits);

// unshift: add an item to the benigging (앞에서부터 데이터 넣음)
fruits.unshift('🍓', '🍋');
console.log(fruits);

// shift: remove an item from the benigging (앞에서부터 데이터 빼기)
fruits.shift();
fruits.shift();
console.log(fruits);
```

**note!! shift, unshift are slower than pop, push**
**pop, push를 사용하는게 더 좋다**
**제일 뒤에서 접근하는것은 정말 빠르고 중간에 데이터를 넣고 빼는것도 index를 활용하기 때문에 빠르다. but 전체의 데이터들이 움직이고 shift 되면 더 느릴수 밖에 없다. 배열의 길이가 길면 길수록 전체적으로 움직여야하는것이 많기 때문에 더 느림.**

```js
// splice: remove an item by index position(지정된 위치에서 데이터 지우기)
// splice(시작하는 인덱스, 몇개나 지울건지 지정(값을 지정해도 되고 안해도 됨))
//  fruits.splice(1); 만 할경우 시작하는 인덱스 제외한 나머지 전부 지워짐
fruits.push('🍓', '🍑', '🍋');
console.log(fruits);
fruits.splice(1, 1);
console.log(fruits);
fruits.splice(1, 0, '🍏', '🍉');
// 지우고 난 자리에 원하는 데이터 사과와 수박을 넣어줌
console.log(fruits);

// combine two arrays
const fruits2 = ['🍐', '🥥'];
const newFruits = fruits.concat(fruits2);
console.log(newFruits);
```

##### 5. Searching
```js
// indexOf: find the index (베열안에 해당하는 데이터가 없으면 -1이 출쳑됨)
console.clear();
console.log(fruits);
console.log(fruits.indexOf('🍎'));
console.log(fruits.indexOf('🍉'));
console.log(fruits.indexOf('🥥'));

// includes (배열에 데이터의 유무를 true, false로 알려줌)
console.log(fruits.includes('🍉'));
console.log(fruits.includes('🥥'));

// lastIndexOf
console.clear();
fruits.push('🍎');
console.log(fruits);
console.log(fruits.indexOf('🍎')); //똑같은 데이터가 있을 경우 첫번째 인덱스 리턴
console.log(fruits.lastIndexOf('🥥')); // 똑같은 데이터가 있을 경우 마지막 인덱스 리턴
```


> ## 출처 : 드림코딩 엘리
<!-- Link -->
Click [Here](https://youtu.be/yOdAVDuHUKQ)
