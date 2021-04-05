---
title: React) useEffect
author: MyungSeung Kim
date: 2021-04-04 14:00:00 +0900
categories: [Web, React]
tags: [web, react, jsx, frontend]
math: true
mermaid: true
image:

---
component가 mount, update, unmount 될 때, **useEffect**를 사용하여 자동으로 코드를 실행시킬 수 있다.

## useEffect
---

```jsx
import { useEffect } from  'react';
function Comp() { 
	useEffect(()=>{ 
		// 1
	});
	useEffect(()=>{ 
		// 2
		return ()=> {
			// 4
		}
	}, []);
	useEffect(()=>{ 
		// 3
		return ()=> {
			// 5
		}
	}, [state]);
```
1. 컴포넌트가 mount, update 될 때 실행
2. 컴포넌트가 mount 될 때 한번만 실행
3. 컴포넌트가 mount, state가 변경 될 때 실행
4. 컴포넌트가 unmount될 때 한번만 실행
5. 컴포넌트가 
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
JSX안에서 사용 불가하고 history stack을 활용하기에 유용한 기능들이 많다.
대표적인 예로 뒤로가기인 `goBack()`이 있다.
<br/>

## useParams
url Parameters들을 쉽게 가져올 수 있는 함수다.
`Route path="/:p1/:p2"` 일 때, 
```jsx
let { p1, p2 } = useParams();
```
위처럼 파라미터를 변수에 저장할 수 있다.

`useParams()`는 key와 value를 반환하기에 반드시 변수 이름을 일치시켜 줘야 한다.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwMjA4NTUyNjksNzAyMjA4MDYsLTU4MD
AxNjQ4OV19
-->