---
title: JSX와 state, Component
author: MyungSeung Kim
date: 2021-03-31 19:12:00 +0900
categories: [Web, React]
tags: [web, react, jsx]
math: true
mermaid: true
image:

---

React에서는 HTML 대신 JSX를 사용한다!


## JSX
---

```jsx
function App(){
  return ( 
    <div>html소스</div>
  )	 
}
```
App.js 의 App함수에 HTML소스를 return하면 됨!
<br/>

#### class
JSX에서는 __class__ 가 아닌 __className__

#### data binding
```jsx
function App(){
  var data = '데이터바인딩';
    return ( 
    <div>{data}</div> //'데이터바인딩'이 div에 들어감
  )	 
}
```
#### style
```jsx
<div style={ {fontSize : '50px', textAlign : 'center'} }> </div>
```
모든 propertyName은 Hypen 대신 __camelCase__ 로!
<br/>
## state
---
JSX에서 data binding 시 일반 변수가 아닌 state를 사용한다.

어째서?

 __state 안의 data가 변경되면 state가 포함된 HTML을 자동으로 rerendering 해준다!__ 
 
이 얼마나 간편한가
```jsx
import React, { useState } from 'react';

function App() {
  let [alert, alertEdit] = useState(false);
  
  return ({ 
    alert ?
	  <div> 알림!! </div>
	  : null
  })
}
```
 __useState__ 를 사용하여 state를 생성한다. (import 필수)
 
 _alertEdit()_ 으로 `alert`를 변경시키면, `alert`가 포함된 HTML이 자동으로 rerendering 된다.
 <br>
>destructing?
>```jsx
>var [name, age] = ['Kim', 20];
>```
>array 안의 데이터를 쉽게 변수에 선언 가능!

## Component
하나의 *div*를 하나의 *function*으로 줄일 수 있다.

이 *function*에서 return된 *div*를  **Component** 라고 부른다.
```jsx
function Comp(){ 
  return ( 
    <div>
      블라블라블랄랄라
    </div>
  )
}
function App(){ 
  return (
    <div> 
      <Comp></Comp>
    </div> 
  )
} 
```
`App()`에서 `<Comp></Comp>`가 하나의 **Component!**

`App()`도


#### 주의

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTI3MTk3NDg5MF19
-->