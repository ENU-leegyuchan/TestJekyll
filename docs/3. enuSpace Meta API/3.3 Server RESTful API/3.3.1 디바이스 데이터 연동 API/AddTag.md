---
layout: default
title: AddTag
parent: 3.3.1 디바이스 데이터 연동 API
grand_parent: 3.3 Server RESTful API
grand_grand_parent: 3. enuSpace Meta API
---

# Server API 

## AddTag(Param1)

    - 테이블에 태그를 추가합니다.

### Protocol / Method
    - HTTP/POST
    - application/json

### Parameter (인자)

    - Param1 : Json 파일포맷

```Json
{
    "APIKEY":"APIKEY",
    "TagInfoList" : [
        {
            "Tag" : "태그1",
            "Type" : "데이터 타입(string, int, double)",
            "Description" : "태그 설명",
            "IOType" : "디바이스 Input/Output 타입", 
            "Value" : "초기값"
        },
        {
            "Tag" : "태그2",
            "Type" : "데이터 타입(string, int, double)",
            "Description" : "태그 설명",
            "IOType" : "디바이스 Input/Output 타입",
            "Value" : "초기값"
        }
    ]
}
```	 


### Return (반환값)

	- 데이터 Tag의 정보
```Json
{
    "Result" : "OK",
    "Msg" : ""
}
```

### Remark (주의사항)
    - 

### Example (API 사용 예시)
    - HTTP/POST https://127.0.0.1:3000/api/DAQ/deivce/AddTag
```Json
{
    "APIKEY":"_3qd1a3hfko5163ceb2ad174vq1u95yz3",
    "TagInfoList" : [
        {
            "Tag" : "Tag1",
            "Type" : "int",
            "Description" : "Description1",
            "IOType" : "output",
            "Value" : "30"
        },
        {
            "Tag" : "Tag2",
            "Type" : "double",
            "Description" : "Description2",
            "IOType" : "input"
        }
    ]
}
```