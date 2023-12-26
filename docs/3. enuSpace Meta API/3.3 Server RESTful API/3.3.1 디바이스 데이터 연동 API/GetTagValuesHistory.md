---
layout: default
title: GetTagValuesHistory
parent: 3.3.1 디바이스 데이터 연동 API
grand_parent: 3.3 Server RESTful API
grand_grand_parent: 3. enuSpace Meta API
---

# Server API 

## GetTagValuesHistory(Param1)

    - 특정 태그의 데이터를 시작 시간부터 끝 시간까지 일정 간격으로 나누어 반환합니다.

### Protocol / Method
    - HTTP/POST
    - application/json

### Parameter (인자)

    - Param1 : Json 파일포맷

```Json
{
    "APIKEY":"APIKEY",
    "Tag" : "태그명",
    "StartTime" : "2023-05-01 00:00:00",
    "EndTime" : "2023-05-30 00:00:00",
    "Duration" : 5000
}
```	 


### Return (반환값)

	- 데이터 Tag의 정보
```Json
{
    "Msg": "",
    "Data": [
        {
            "Value": "10.0",
            "TimeStamp": "2023-05-15T18:31:35",
            "Result": "Ok"
        },
        {
            "Value": "11.0",
            "TimeStamp": "2023-05-15T18:31:40",
            "Result": "Ok"
        },
        {
            "TimeStamp": "2023-05-15T18:31:45",
            "Result": "Fail"
        }
    ]
}
```

### Remark (주의사항)
    - Interval과 SetUrl은 AcquisitionType이 Master일 때만 유효

### Example (API 사용 예시)
    - HTTP/POST https://127.0.0.1:3000/api/DAQ/device/GetTagValuesHistory
```Json
{
    "APIKEY":"_3qd1a3hfko5163ceb2ad174vq1u95yz3",
    "Tag" : "LED_1",
    "StartTime" : "2023-07-01 00:00:00",
    "EndTime" : "2023-07-03 00:00:00",
    "Duration" : 5000
}
```