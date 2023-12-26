---
layout: default
title: GetTagValues
parent: 3.3.1 디바이스 데이터 연동 API
grand_parent: 3.3 Server RESTful API
grand_grand_parent: 3. enuSpace Meta API
---

# Server API 

## GetTagValues(Param1)

    - 태그의 가장 최신 값을 요청하는 API입니다.

### Protocol / Method
    - HTTP/POST
    - application/json

### Parameter (인자)

    - Param1 : Json 파일포맷

```Json
{
    "APIKEY":"APIKEY",
    "Tags":[
            "태그1",
            "태그2"

    ]
}
```	 


### Return (반환값)

	- 데이터 Tag의 정보
```Json
{
    "Msg": "",
    "Data": [
        {
            "Data": [
                {
                    "Tag": "태그1",
                    "Value": "11.0",
                    "TimeStamp": "2023-05-16T03:32:54.419",
                    "Result": "Ok"
                }
            ],
            "Table": "테이블1"
        },
        {
            "Data": [
                {
                    "Tag": "태그2",
                    "Value": "10.0",
                    "TimeStamp": "2023-05-16T03:32:54.419",
                    "Result": "Ok"
                }
            ],
            "Table": "테이블2"
        }
    ],
    "Result": "Ok"
}
```

### Remark (주의사항)
    - none

### Example (API 사용 예시)
    - HTTP/POST https://127.0.0.1:3000/api/DAQ/Device/GetTagValues
```Json
{
    "APIKEY":"_3qd1a3hfko5163ceb2ad174vq1u95yz3",
    "Tags":[
            "LED_1",
            "Temp_2"
    ]
}
```