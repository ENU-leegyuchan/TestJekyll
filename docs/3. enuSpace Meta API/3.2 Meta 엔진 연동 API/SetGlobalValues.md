---
layout: default
title: SetGlobalValues
parent: 3.2 Meta 엔진 연동 API
grand_parent: 3. enuSpace Meta API
---

# WASM API 

## SetGlobalValues(Param1)

    - global 전역변수에 등록된 변수리스트에 값을 할당하는 함수입니다.

<br>

### Parameter (인자)

    - Param1 : Json 파일포맷

```Json
[
	{
		"Table" : "테이블명1",
		"Data" : 
		[
			{
				"TagName" : "태그이름1",
				"Value" : "값"
			},
			{
				"TagName" : "태그이름2",
				"Value" : "값"
			},
		]
	},
	{
		"Table" : "테이블명2",
		"Data" : 
		[
			{
				"TagName" : "태그이름1",
				"Value" : "값"
			},
			{
				"TagName" : "태그이름2",
				"Value" : "값"
			},
		]
	}	
]
```	 

### Return (반환값)

	- 


### Remark (주의사항)
    - WASM Module 함수인 SetGlobalValues(Json)를 아래의 형태와 같이 js에서 호출하기위한 함수로 선언하여 사용하여야 함.
	(g_enuSpace : 모듈객체)
	사용 시 주의사항 : 여러 Table과 여러 Tag를 한번에 값 할당을 할 수 있게 하기위해 배열 처리한 것 주의.



### Example (함수사용 예시)

```js
//선언
function User_SetGlobalValues(Json){
    g_enuSpace.SetGlobalValues(Json);
}

//사용
function Call_ExternalFunctionJS(strJson)
{
	// 예시 1
	 User_SetGlobalValues("[{Table: "TABLE1", Data: [{TagName: "C27CM_POS", Value:"123"}]}]"}

 	// 예시 2
	 User_SetGlobalValues("[{Table: "TABLE1", Data: [{TagName: "C54CM_POS”, Value:”12”},{TagName: "C60CM_POS", Value:"34"}]}, {Table: "TABLE2", Data: [{TagName: "C63CM_POS", Value:"56"},{TagName: "C8CM_POS", Value:"78"}]}]"}
}

```

