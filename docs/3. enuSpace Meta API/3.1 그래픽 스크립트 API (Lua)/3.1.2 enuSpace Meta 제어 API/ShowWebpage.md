---
layout: default
title: ShowWebpage
parent: 3.1.2 enuSpace Meta 제어 API
grand_parent: 3.1 그래픽 스크립트 API (Lua)
grand_grand_parent: 3. enuSpace Meta API
---

# Lua API 

## ShowWebpage(Param1)

    - Web page 주소를 읽어 iframe을 통해 화면을 호출하는 함수입니다.

<br>

### Parameter (인자)

    - Param1 : path

### Return (반환값)

	- none

### Remark (주의사항)
    - iframe 사용을 차단한 Web page는 호출할 수 없습니다.

### Example (함수사용 예시)

```lua
	function _onclick()
        ShowWebpage("https://www.youtube.com/embed/4dwpcSRX-1s") 
	end
```
