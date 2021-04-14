---
title: "padding & margin & box-sizing"
categories:
  - Github blog
---

## padding & margin & box-sizing

### padding
padding은 border와 content사이에 존재하는 여백을 의미한다.
즉, 박스의 안쪽 여백을 말한다.

### margin
margin은 박스의 바깥쪽 여백을 의미한다.
즉, 엘리먼트들의 간격을 의미한다.

### content-box
실제 내용을 포함하는 영역<br>
ex) width를 200px로 설정했다고 할지라도 전체 너비가 200px이 되는 것이 아닌,<br>
여기에 padding과 border-width가 더해져서 그려지게 된다.

### box-sizing
box-sizing property는 width, height를 어느 영역까지 포함 할 것인가를 결정하는 property.<br>
이 box-sizing의 기본값이 content-box이기 때문에 width, height에 값을 지정 했을때 그 값이 곧 content영역의 너비와 높이가 된다.

#### content-box에서 width:100%일 때의 문제
CSS에서 width 속성을 100%로 주면 부모의 width 만큼 너비가 설정된다.<br>
하지만 content-box일 때 width: 100%에 이어 padding이나 border를 주게 될 경우 부모의 영역을 초과해서 너비가 정해지는 문제가 생길 수 있다.<br>
이런 문제를 해결하기 위해서는 box-sizing을 border-box로 설정하거나 width를 auto로 설정하여 해결할 수 있다.<br>
width의 기본 값은 auto이므로 width를 아예 적어주지 않아도 정상적으로 동작한다.


> ## 출처 :
<!-- Link -->
Click [Here](https://seungwoohong.tistory.com/25)<br>
Click [Here](https://ofcourse.kr/css-course/box-sizing-%EC%86%8D%EC%84%B1)





