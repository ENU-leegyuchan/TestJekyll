---
layout: default
title: GetSelectedTag
parent: 3.3.1 디바이스 데이터 연동 API
grand_parent: 3.3 Server RESTful API
grand_grand_parent: 3. enuSpace Meta API
---

# Server API 

## GetSelectedTag(Param1)

    - 원하는 태그의 정보를 반환합니다

### Protocol / Method
    - HTTP/POST
    - application/json

### Parameter (인자)

    - Param1 : Json 파일포맷

```Json
{
    "APIKEY":"APIKEY",
    "Tags" : [
            "태그1",
            "태그2"
    ]
}
```	 


### Return (반환값)

	- 데이터 Tag의 정보
```Json
[
    {
        "table": "테이블1",
        "tag": "태그1",
        "description": "태그1 설명",
        "value": "10.0",
        "type": "string",
        "variableName": "태그1"
    },
    {
        "table": "테이블1",
        "tag": "태그2",
        "description": "태그2 설명",
        "value": "10.0",
        "type": "string",
        "variableName": "태그2"
    }
]
```

### Remark (주의사항)
    - none

### Example (API 사용 예시)
    - HTTP/POST https://127.0.0.1:3000/api/DAQ/device/GetSelectedTag
```Json
{
    "APIKEY":"_3qd1a3hfko5163ceb2ad174vq1u95yz3",
    "Tags" : [
            "LED_1",
            "Temp_2"
    ]
}
```