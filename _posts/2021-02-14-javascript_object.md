---
title: "Jvascript object"
categories:
  - Github blog
---

## Jvascript object
##### 1. object = { key : value }; key와 value의 집합체
```js
const ellie = { name: 'ellie', age: 4 };
print(ellie);
```

##### 2. Computed properties
```js
// key should be always string
console.log(ellie.name);
console.log(ellie['name']);
ellie['hasJob'] = true;
console.log(ellie.hasJob);

function printValue(obj, key) {
  console.log(obj[key]);
}
printValue(ellie, 'name');
printValue(ellie, 'age');
```

##### 3. Property value shorthand
```js
const person1 = { name: 'bob', age: 2 };
const person2 = { name: 'steve', age: 3 };
const person3 = { name: 'dave', age: 4 };
const person4 = new Person('elile', 30);
console.log(person4);
```

##### 4.Constructor Function
```js
function Person(name, age) {
  // this = {};
  this.name = name;
  this.age = age;
  // return this;
}
```

##### 5. in operator: property existence check (key in obj)
```js
console.log('name' in ellie);
console.log('age' in ellie);
console.log('random' in ellie);
console.log(ellie.random);
```

##### 6. for..in vs for..of
```js
// for in(key in obj)
// 모든 key들을 받아와 처리하고 싶을 때 for in
console.clear(); //이전것들 지워짐
for (let key in ellie) {
  console.log(key);
}


// for of (value of iterable)
// case1 case2 for문보다 더 쉽고 효율적임
const array = [1, 2, 4, 5];
for (let value of array) {
  console.log(value);
}

// case2
const array = [1, 2, 4, 5];
for (let i = 0; i < array.length; i++) {
  console.log(array[i]);
}
```


##### 7. Fun cloning
```js
// Object.assign(dest, [obj1, obj2, obj3...])
const user = { name: 'ellie', age: '20' };
const user2 = user;
console.log(user);

// old way
const user3 = {};
for (let key in user) {
  user3[key] = user[key];
}
console.clear();
console.log(user3);

const user4 = Object.assign({}, user);
console.log(user4);

// another example
const fruit1 = { color: 'red' };
const fruit2 = { color: 'blue', size: 'big' };
const mixed = Object.assign({}, fruit1, fruit2);
console.log(mixed.color);
console.log(mixed.size);
```




> ## 출처 : 드림코딩 엘리
<!-- Link -->
Click [Here](https://youtu.be/1Lbr29tzAA8)
