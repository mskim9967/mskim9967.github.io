---
title: props와 import/export
author: MyungSeung Kim
date: 2021-04-01 14:52:00 +0900
categories: [Web, React]
tags: [web, react, jsx, frontend]
math: true
mermaid: true
image:

---

Component에 data binding을 위해서는 props 문법을 사용해야 한다
<br/>

## props
---

```jsx
function Comp(props) {
	let [data, editData] = useState("데이타");		
	return (
		<div>
			<Comp data={data} data2="데이타2"></Comp>
		</div>
	)
} 

function Comp(props) {
	return (
		<div>
			{ props.data + props.data2 }
		</div>
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
<br/>

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

`App()`도 결국 하나의 **Component**를 반환! (*index.js*를 보면 알 수 있음)
<br/>

#### 주의
- 마구 남발하면 data binding하기 복잡해질 수도 있음(props로 data를 넘겨줘야 하기 떔시
-  항상 하나의 `<div>`를 반환해야함!
-  그게 싫으면 `<> 블라블라 </>` 도 가능! (fragments 문법)


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE0NDE5MTQzMzJdfQ==
-->