---
layout: default
title: DeleteTag
parent: 3.3.1 디바이스 데이터 연동 API
grand_parent: 3.3 Server RESTful API
grand_grand_parent: 3. enuSpace Meta API
---

# Server API 

## DeleteTag(Param1)

    - 테이블의 태그를 삭제합니다.

### Protocol / Method
    - HTTP/POST
    - application/json

### Parameter (인자)

    - Param1 : Json 파일포맷

```Json
{
    "APIKEY":"APIKEY",
    "TagList" : [
        "태그1",
        "태그2"
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
    - HTTP/POST https://127.0.0.1:3000/api/DAQ/device/DeleteTag
```Json
{
    "APIKEY":"_3qd1a3hfko5163ceb2ad174vq1u95yz3",
    "TagList" : [
        "LED_1",
        "Temp_2"
    ]
}
```