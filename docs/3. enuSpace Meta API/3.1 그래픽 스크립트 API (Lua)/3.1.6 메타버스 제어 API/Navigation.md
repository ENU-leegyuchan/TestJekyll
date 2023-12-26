---
layout: default
title: Navigation
parent: 3.1.6 메타버스 제어 API
grand_parent: 3.1 그래픽 스크립트 API (Lua)
grand_grand_parent: 3. enuSpace Meta API
---

# Lua API 

## Navagation(Param1, ...)

    - 메타버스 모드에서 아바타를 다른 화면으로 이동하기 위한 함수
    - 가변인자 설정에 따라 해당 화면에서 아바타가 최초 생성될 위치를 지정할 수 있음

<br>

### Parameter (인자)

    - Param1 : 픽쳐 이름
    - Param2 : 가변 인자 ( 0 ~ 2개)

### Return (반환값)

	- none

### Remark (주의사항)

    - none

### Example (함수사용 예시)

```lua
    -- 해당 함수를 발생시킨 객체의 위치와 동일하게 Test픽쳐에서 생성
    -- ex) Navagation함수를 translate(100,100)인 객체가 실행을 시켰을 경우, Test픽쳐에의 100, 100 좌표에 아바타가 생성
	function _onclick()
		Navagation("picture\\Test.svg")
	end
    
    -- Test픽쳐의 id가 "ID_RECT"인 객체의 위치에 아바타가 생성
	function _onclick()
		Navagation("picture\\Test.svg", "ID_RECT")
	end
    
    -- Test픽쳐의 1920, 1080 좌표에 아바타가 생성
	function _onclick()
		Navagation("picture\\Test.svg", 1920, 1080)
	end
```
