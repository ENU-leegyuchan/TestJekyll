---
layout: default
title: GetTagValues
parent: 3.1.3 데이터 연동 API
grand_parent: 3.1 그래픽 스크립트 API (Lua)
grand_grand_parent: 3. enuSpace Meta API
---

# Lua API 

## GetTagValues(Param1, Param2)

    - DAQ(데이터취득)시스템으로부터 데이터를 요청하는 함수입니다.

<br>

### Parameter (인자)

    - Param1 : DB Table Name
    - Param2 : Lua Array


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
            "TagName" : "태그이름1",
            "Value" : "값1",
            "TimeStamp":"2023.04.23:34:00:00"
            "Result":"OK"
         },
         {
            "TagName" : "태그이름2",
            "Value" : "N/A",
            "TimeStamp" : "2023.04.23:34:00:00"
            "Result" : "FAIL"
         }
      ]
   }
   {
      "Table" : "테이블명2",
      "Data" :
      [
         {
            "TagName" : "태그이름1",
            "Value" : "값1",
            "TimeStamp":"2023.04.23:34:00:00"
            "Result":"OK"
         },
         {
            "TagName" : "태그이름2",
            "Value" : "N/A",
            "TimeStamp" : "2023.04.23:34:00:00"
            "Result" : "FAIL"
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
		local data = {"tag1", "tag2", "tag3"}
      ID_TEXT.text = GetTagValues("table",data)
	end
```
