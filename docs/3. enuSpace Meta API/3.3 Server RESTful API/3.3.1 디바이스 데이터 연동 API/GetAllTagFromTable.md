---
layout: default
title: GetAllTagFromTable
parent: 3.3.1 디바이스 데이터 연동 API
grand_parent: 3.3 Server RESTful API
grand_grand_parent: 3. enuSpace Meta API
---

# Server API 

## GetAllTagFromTable(Param1)

    - 테이블에 속한 모든 태그의 리스트를 반환합니다.

### Protocol / Method
    - HTTP/POST
    - application/json

### Parameter (인자)

    - Param1 : Json 파일포맷

```Json
{
    "APIKEY":"APIKEY"
}
```


### Return (반환값)

	- 데이터 Tag의 정보
```Json
[
    {
        "Table": "테이블명",
        "Tag": "태그1",
        "Description": "태그1 설명",
        "Value": null,
        "Type": "string",
        "IOType": "input",
        "VariableName": "태그1"
    },
    {
        "Table": "테이블명",
        "Tag": "태그2",
        "Description": "태그2 설명",
        "Value": "10.0",
        "Type": "double",
        "IOType": "input",
        "VariableName": "태그2"
    }
]
```

### Remark (주의사항)
    - none

### Example (API 사용 예시)

    - HTTP/POST https://127.0.0.1:3000/api/DAQ/device/GetAllTagFromTable
```Json
{
    "APIKEY":"_3qd1a3hfko5163ceb2ad174vq1u95yz3"
}
```