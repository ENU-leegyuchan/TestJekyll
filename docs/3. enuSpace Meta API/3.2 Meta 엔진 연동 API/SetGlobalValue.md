---
layout: default
title: SetGlobalValue
parent: 3.2 Meta 엔진 연동 API
grand_parent: 3. enuSpace Meta API
---

# WASM API 

## SetGlobalValue(Param1)

    - global 전역변수에 등록된 변수에 값을 할당하는 함수입니다.

<br>

### Parameter (인자)

    - Param1 : 테이블 명
	- Param2 : 태그명
	- Param3 : 태그 값 

### Return (반환값)

	- 

### Remark (주의사항)
    - WASM Module 함수인 SetGlobalValue(Table, Tag, Value)를 아래의 형태와 같이 js에서 호출하기위한 함수로 선언하여 사용하여야 함. (g_enuSpace : 모듈객체)


### Example (함수사용 예시)

```js
	//선언
	function User_SetGlobalValue(Table, Tag, Value)
	{
		g_enuSpace.SetGlobalValue(Table, Tag, Value);
	}

	//사용
	function Call_ExternalFunctionJS(strJson)
	{
 	   	// 사용자 정의 로직 추가.
		 User_SetGlobalValue("TABLE", "C24CM_POS", "140");
	}
```

