---
layout: default
title: SetScheduleActivation
parent: 3.3.1 디바이스 데이터 연동 API
grand_parent: 3.3 Server RESTful API
grand_grand_parent: 3. enuSpace Meta API
---

# Server API 

## SetScheduleActivation(Param1)

    - 테이블의 AcquisitionType이 Master일 경우 데이터 적재 스케쥴링 활성화/비활성화 선택

### Protocol / Method
    - HTTP/POST
    - application/json

### Parameter (인자)

    - Param1 : Json 파일포맷

```Json
{
    "APIKEY" : "APIKEY",
    "ACTIVATION":"TRUE/FALSE"
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
    - True 설정 시 DB 적재 / False 설정 시 DB 미적재

### Example (API 사용 예시)

    - HTTP/POST https://127.0.0.1:3000/api/DAQ/Device/SetScheduleActivation
```Json
{
    "APIKEY":"_3qd1a3hfko5163ceb2ad174vq1u95yz3",
    "ACTIVATION":"TRUE"
}
```