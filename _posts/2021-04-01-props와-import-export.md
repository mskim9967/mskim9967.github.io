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


Component에 data binding을 위해서는 props 문법을 사용해야 한다.
<br/>

또한 외부 jsx 파일의 함수, 변수 등을 불러올 때는 import/export르 사용해야 한다.
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
띄어쓰기로 구분하여 여러개의 data를 보내줄 수 있다
<br/>

## export/import
---

```jsx
// dataExport.js
var data = ["aa", "bb", "cc"];
export default data;

// dataImport.js
import dataImport from "./dataExport.js
```
또는 
```jsx
// dataExport.js
var data = ["aa", "bb", "cc"];
var data2 = "data2;
export { data, data2 };

// dataImport.js
import { data, data2 } from "./dataExport.js
```
`export default`를 사용한다면 하나의 객체만 내보낼 수 있지만, `export {}` 를 사용한다면 여러개의 객체를 내보낼 수 있다.

또한 `export default`를 사용하면 `import`시 변수명을 자유롭게 작성할 수 있지만, `export {}`를 사용한다면 변수명은 `export {}` 안의 변수명 그대로 사용해야 한다.
<!--stackedit_data:
eyJoaXN0b3J5IjpbOTg5NTMxNDcwLDEwMjQ5Mzg1NjQsLTE0ND
E5MTQzMzJdfQ==
-->