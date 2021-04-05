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

5. state가 변경되어 컴포넌트가 update되기 전 실행
<br/>
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTkzMDcwMjI1OCw3MDIyMDgwNiwtNTgwMD
E2NDg5XX0=
-->