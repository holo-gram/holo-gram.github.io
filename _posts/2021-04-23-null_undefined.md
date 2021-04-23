---
title: "null vs undefined"
categories:
  - Github blog
---

## null vs undefined
- **undefiend** : 변수는 존재하나, 어떠한 값으로도 할당되지 않아 <code>자료형이 정해지지(undefined) 않은 상태</code>.
- **null** : 변수는 존재하나, null로 (값이) 할당된 상태. 즉 null은 <code>자료형이 정해진(defined) 상태</code>.

## null == undefined
```js
null == undefined //true ( 자바스크립트 == 연산자의 자동 형변환 )
null === undefined //false (완벽비교, 데이터 타입끼리 동일한지 비교)
```

> ## 출처 :
<!-- Link -->
Click [Here](https://siyoon210.tistory.com/148)