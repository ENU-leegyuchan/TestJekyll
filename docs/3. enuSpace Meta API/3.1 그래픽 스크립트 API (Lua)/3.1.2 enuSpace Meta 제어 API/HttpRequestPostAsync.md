---
layout: default
title: HttpRequestPostAsync
parent: 3.1.2 enuSpace Meta 제어 API
grand_parent: 3.1 그래픽 스크립트 API (Lua)
grand_grand_parent: 3. enuSpace Meta API
---

# Lua API 

## HttpRequestPostAsync(Param1, Param2, Param3)

    - 외부서버에 Http 프로토콜을 이용하여 데이터를 비동기 요청합니다. (WASM Call)

<br>

### Parameter (인자)

    - Param1 : URL address
	- Param2 : Body
	- Param3 : Callback function name

### Return (반환값)

	- none
	
### Remark (주의사항)
	- callback으로 실행시켜 줄 함수는 HttpRequestPostAsync 함수가 실행된 객체에 존재해야 함
	- callback 함수는 비동기 요청 후 응답 메세지를 받을 파라미터가 필요함에 따라 파라미터를 하나만 사용해야 함

### Example (함수사용 예시)

```lua
	function _onclick()
		local data = [[{"URL": "user contents"}]]	
		HttpRequestPostAsync("https://localhost:7031/Example/PostDataExample", data, "_userfunction")
	end
	
	function _userfunction(msg)
		jsondcode = Json.decode(msg)
		dimsi = jsondcode.shape.dims[1]
		PrintMessage(tostring(dimsi))
	end
```