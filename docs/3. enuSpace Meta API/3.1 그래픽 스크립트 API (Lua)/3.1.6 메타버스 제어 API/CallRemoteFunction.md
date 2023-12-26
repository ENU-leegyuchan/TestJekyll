---
layout: default
title: CallRemoteFunction
parent: 3.1.6 메타버스 제어 API
grand_parent: 3.1 그래픽 스크립트 API (Lua)
grand_grand_parent: 3. enuSpace Meta API
---

# Lua API 

## CallRemoteFunction(Param1, Param2, ...)

    - 메타버스 모드에서 모든 클라이언트에게 함수 작동 명령을 내리는 함수
	- CallRemoteFunction 파라미터로 실행시킬 함수를 지정하고 실행 시 모든 클라이언트에게 지정한 함수를 실행하라는 명령을 전달.

<br>

### Parameter (인자)

    - Param1 : 픽쳐 이름 ("picture\\Test.svg")
    - Param2 : 객체 ID
    - Param3 : Param2에서 지정한 객체의 실행시킬 함수
	- Param4 : 가변 인자 (Param3의 함수에 전달할 파라미터)

### Return (반환값)

	- none

### Remark (주의사항)

	1. Param2는 CallRemoteFunction을 실행시킨 객체가 속한 layer의 객체만 선택이 가능함 (다음 케이스 불가능 : use내부 -> use외부 or use외부 -> use내부)
    2. Param1에서 "this"로 사용 했을 경우 CallRemoteFunction을 실행하는 픽쳐를 전달 
	3. Param2에서 "this"로 사용 했을 경우 CallRemoteFunction을 실행하는 객체를 전달
	4. Param1, Param2를 모두 빈칸으로 두었을 경우 전역으로 선언된 함수에 대해서 사용가능

### Example (함수사용 예시)

```lua
	function _onclick()
		CallRemoteFunction("picture\\Test.svg", "this", "TestFunc", true)
	end
    
	function TestFunc(Flag)
		if Flag then
			PrintMessage("True")
		end
	end

	-- 주의사항 4번 예시
	function _onclick()
		CallRemoteFunction("", "", "ShowMarkdown", "document/document.md")
	end

```
