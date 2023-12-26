---
layout: default
title: UpdateTag
parent: 3.3.1 디바이스 데이터 연동 API
grand_parent: 3.3 Server RESTful API
grand_grand_parent: 3. enuSpace Meta API
---

# Server API 

## UpdateTag(Param1)

    - 테이블의 태그 정보를 변경합니다.

### Protocol / Method
    - HTTP/POST
    - application/json

### Parameter (인자)

    - Param1 : Json 파일포맷

```Json
{
    
    "APIKEY":"APIKEY",
    "Tag" : "변경 전 태그명",
    "Data" : {
        "tag" : "변경할 태그명",
        "type": "변경할  타입",
        "description": "변경할 설명",
        "IOType": "변경할 IOType"
    }
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
    - Tag, Description, Type, VariableName, IOType에 해당하는 Attribute를 지원합니다.

### Example (API 사용 예시)
    - HTTP/POST https://127.0.0.1:3000/api/DAQ/device/UpdateTag
```Json
{
    "APIKEY":"_3qd1a3hfko5163ceb2ad174vq1u95yz3",
    "Tag" : "LED_1",
    "Data" : {
        "tag" : "Bright_Pin_1",
        "type": "double",
        "description": "bright_pin",
        "IOType": "Input"
    }
}
```