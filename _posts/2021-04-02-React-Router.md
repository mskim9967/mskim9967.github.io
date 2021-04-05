---
title: React) React Router
author: MyungSeung Kim
date: 2021-04-02 14:52:00 +0900
categories: [Web, React]
tags: [web, react, jsx, frontend]
math: true
mermaid: true
image:

---

react-router-dom 라이브러리를 사용하여 React에서 routing을 할 수 있다.

이는 실제로 다른 HTML 파일을 보여주는 것이 아닌, 하나의 HTML 내용을 수정하여 다른 HTML 파일을 보여주는 것처럼 흉내내는 것이다.
또한 화면이 깜빡이는 새로고침 없이 주소를 변경할 수 있어 웹앱에 최적화 되어있다.

`npm install react-router-dom`으로 설치 가능하다.
<br/>

## BrowserRouter
---

```jsx
// index.js
import { BrowserRouter } from  'react-router-dom';

ReactDOM.render( 
	<React.StrictMode>
		<BrowserRouter>
			<App/> 
		</BrowserRouter>
	</React.StrictMode>
	document.getElementById('root')
);
```
```jsx
/// App.js
import { Route, Switch, useHistory, Link } from 'react-router-dom';

function App() {
	return (
		<div>
			<Route exact path="/" component={ Comp }></Route>
			
			<Route path="/yeah">
				yyeeeaaah
			</Route>
		</div>
	)
}
```
#### component
`<Route>` 안에 **component** property를 사용하여 해당 컴포넌트를 바로 넣을 수 있다. 코드 읽기 편해질듯! 
#### exact
`exact`를 사용하지 않는다면 **&#47;yeah**로 접속하였을 때   
**&#47;** 의 Comp도 같이 표시된다. 
`exact`를 사용한다면 해당 경로와 정확히 일치하는 Component만 보여진다.
<br/>

## Switch
```jsx
function App() {
	return (
		<div>
			<Switch>
				<Route path="/" component={ Comp }></Route>
				<Route path="/yeah">
					yyeeeaaah
				</Route>
			</Switch>
		</div>
	)
}
```
`Switch`를 사용하면 `exact`를 사용하지 않고 url과 일치하는 한가지 내용만 보여줄 수 있다.
<br/>

## Link
```jsx
<Link to="/">Home</Link>
```
요소 혹은 컴포넌트를 Link 태그로 감싼 뒤 to 속성에 경로를 지정해주면, 해당 링크로 새로고침 없이 이동할 수 있다.
<br/>

## useHistory
변수에 `usehistory()`를 저장한 후 함수 안에서 `push()` 메서드로 경로 이동이 가능하다.
JSX안에서 사용 불가하고 

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTk4ODAxMjYxOCwtODY3NjAzNTEyLDM3OD
A4MTc1MywtMTMyMTEzNDY3NiwtNjA0MzgyNzQ0XX0=
-->