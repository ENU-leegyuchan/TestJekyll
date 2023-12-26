---
layout: default
title: SetTagValue
parent: 3.1.3 데이터 연동 API
grand_parent: 3.1 그래픽 스크립트 API (Lua)
grand_grand_parent: 3. enuSpace Meta API
---

# Lua API 

## SetTagValue(Param1, Param2, Param3, ...)

    - DAQ(데이터취득)시스템에 데이터를 적재하는 함수입니다.

<br>

### Parameter (인자)

    - Param1 : DB Table Name
    - Param2 : Tag Name 1
    - Param3 : Tag Value 1
    - ...
    - ParamN : Tag Name N
    - ParamN+1 : Tag Value N


### Return (반환값)

	- 데이터 Tag의 정보
```Json
{
    "Result" : "OK",
    "Msg" : "Bla ~bla~",
}
```

### Remark (주의사항)
    - SetTagValue 사용시 ParamN 과 ParamN+1은 Pair로 동작하며, ParamN은 string, ParamN+1은 string, int, double을 받을 수 있다.

### Example (함수사용 예시)

```lua
	function _onclick()
      ID_TEXT.text = SetTagValue("TableName", "Tag1", "Value1", "Tag2", 3)
	end
```
