---
layout: default
title: SetTagValues
parent: 3.1.3 데이터 연동 API
grand_parent: 3.1 그래픽 스크립트 API (Lua)
grand_grand_parent: 3. enuSpace Meta API
---

# Lua API 

## SetTagValue(Param1, Param2)

    - DAQ(데이터취득)시스템에 데이터를 적재하는 함수입니다.

<br>

### Parameter (인자)

    - Param1 : DB Table Name
    - Param2 : Lua Map


### Return (반환값)

	- 데이터 Tag의 정보
```Json
{
    "Result" : "OK",
    "Msg" : "Bla ~bla~",
}
```

### Remark (주의사항)
    - none

### Example (함수사용 예시)

```lua
	function _onclick()
        local data = {["key1"] = 123, ["key2"] = "value2", ["key3"] = "value3"}
        ID_TEXT.text = SetTagValues("TableName", data)
	end
```
