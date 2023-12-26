---
layout: default
title: SetTagValues
parent: 3.3.1 디바이스 데이터 연동 API
grand_parent: 3.3 Server RESTful API
grand_grand_parent: 3. enuSpace Meta API
---

# Server API 

## SetTagValues(Param1)

    - 현재 시간으로 태그에 값을 추가합니다.

### Protocol / Method
    - HTTP/POST
    - application/json

### Parameter (인자)

    - Param1 : Json 파일포맷

```Json
{
    "APIKEY":"APIKEY",
    "TagsAndValue" :[
        {
            "Tag" : "태그1",
            "Value" : "10.0"
        },
        {
            "Tag" : "태그2",
            "Value" : "12"
        }
    ]
}
```	 

### Return (반환값)

	- 성공
```Json
{
    "Msg":"Tag values are set to druid",
    "Result":"Ok"
}
```
    - MySQL Query 실패
```Json
{
    "Msg":"MySQL,CannotConnectToDatabase",
    "Result":"Fail",
    "Data":"ExceptionMessage"
}
{
    "Msg":"MySQL, ... ",
    "Result":"Fail",
    "Data":"ExceptionMessage"
}
```
    - 데이터 조작 실패
```Json
{
    "Msg":"DBHandle,CannotFindTable",
    "Result":"Fail"
}
{
    "Msg":"DBHandle, ... ",
    "Result":"Fail"
}
```

### Remark (주의사항)
    - none

### Example (API 사용 예시)
    - HTTP/POST https://127.0.0.1:3000/api/DAQ/Device/SetTagValues
```Json
{
    "APIKEY":"_3qd1a3hfko5163ceb2ad174vq1u95yz3",
    "TagsAndValue":[
        {
            "TAG":"LED_1",
            "VALUE":"1"
        },
        {
            "TAG":"TEMP_1",
            "VALUE":"40.8"
        }
        
    ]
}
```