---
layout: default
title: GetTagHistory
parent: 3.1.3 데이터 연동 API
grand_parent: 3.1 그래픽 스크립트 API (Lua)
grand_grand_parent: 3. enuSpace Meta API
---

# Lua API 

## GetTagHistory(Param1, Param2, Param3, Param4, Param5)

    - DAQ(데이터취득)시스템으로부터 히스토리 데이터를 요청하는 함수입니다.

<br>

### Parameter (인자)

    - Param1 : DB Table Name
    - Param2 : Tag Name
    - Param3 : Start Time
    - Param4 : End Time
    - Param5 : Interval (milliseconds)


### Return (반환값)

	- 데이터 Tag의 정보
```Json
{
    "Result" : "OK",
    "Msg" : "Bla ~bla~",
    "Data":
   {
      "Table" : "테이블명1",
      "Data" :
      [
         {
            "Value" : "값1"
            "TimeStamp":"2023.04.23:34:00:00"
         },
         {
            "Value" : "값1"
            "TimeStamp":"2023.04.23:34:00:00"
         }
      ]
   }
}
```

### Remark (주의사항)
    - none

### Example (함수사용 예시)

```lua
	function _onclick()
		ID_bnl4p1.text = GetTagHistory()
	end
```
