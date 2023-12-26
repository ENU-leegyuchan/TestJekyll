---
layout: default
title: HttpRequestGet
parent: 3.1.2 enuSpace Meta 제어 API
grand_parent: 3.1 그래픽 스크립트 API (Lua)
grand_grand_parent: 3. enuSpace Meta API
---

# Lua API 

## HttpRequestGet(Param1)

    - 외부서버에 Http 프로토콜을 이용하여 데이터를 요청합니다. (WASM Call)

<br>

### Parameter (인자)

    - Param1 : URL address

### Return (반환값)

	- 요청 결과의 문자열 데이터

### Remark (주의사항)
    - none

### Example (함수사용 예시)

```lua
	function _onclick()
		ID_TEXT.text = HttpRequestGet("https://finance.naver.com/item/main.naver?code=005930")
	end
```