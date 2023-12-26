---
layout: default
title: PrintMessage
parent: 3.1.2 enuSpace Meta 제어 API
grand_parent: 3.1 그래픽 스크립트 API (Lua)
grand_grand_parent: 3. enuSpace Meta API
---

# Lua API 

## PrintMessage(Param1)

    - log창에 메세지 출력문을 제공하는 함수입니다.

<br>

### Parameter (인자)

    - Param1 : 출력 문자열

### Return (반환값)

	- none

### Remark (주의사항)
    - none

### Example (함수사용 예시)

```lua
	function _onclick()
		local data = string.format("%d개 입니다.", 5)
		PrintMessage(data)
	end
```