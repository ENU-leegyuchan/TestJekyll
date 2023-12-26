---
layout: default
title: HttpRequestPost
parent: 3.1.2 enuSpace Meta 제어 API
grand_parent: 3.1 그래픽 스크립트 API (Lua)
grand_grand_parent: 3. enuSpace Meta API
---

# Lua API 

## HttpRequestPost(Param1, Param2)

    - 외부서버에 Http 프로토콜을 이용하여 데이터를 요청합니다. (WASM Call)

<br>

### Parameter (인자)

    - Param1 : URL address
	- Param2 : Body

### Return (반환값)

	- 요청 결과의 문자열 데이터
	
### Remark (주의사항)
    - none

### Example (함수사용 예시)

```lua
	function _onclick()
		local data = [[{"URL": "user contents"}]]	
		ID_bn4HNB.text = HttpRequestPost("https://localhost:7031/Example/PostDataExample", data)
	end
```