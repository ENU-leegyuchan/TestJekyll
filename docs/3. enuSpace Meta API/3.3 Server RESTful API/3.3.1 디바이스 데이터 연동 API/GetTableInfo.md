---
layout: default
title: GetTableInfo
parent: 3.3.1 디바이스 데이터 연동 API
grand_parent: 3.3 Server RESTful API
grand_grand_parent: 3. enuSpace Meta API
---

# Server API 

## GetTableInfo(Param1)

    - Param1의 API KEY와 상응하는 테이블 1개의 정보를 반환합니다.

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
{
    "Data": [
        {
            "Access": "Public",
            "AcquisitionType": "Slave",
            "Activation": "Deactivated",
            "DBType": "Druid",
            "DeviceIP": "192.168.0.1",
            "GetUrl": "https://192.168.0.1:5000/GetDeviceValues",
            "Id": "Table_ID",
            "Interval": 1000,
            "SetUrl": "https://192.168.0.1:5000/SetDeviceValues",
            "Table": "ardu_table",
            "TagInfoList": []
        }
    ],
    "Msg": "",
    "Result": "Ok"
}
```

### Remark (주의사항)
    - 

### Example (API 사용 예시)

    - HTTP/POST https://127.0.0.1:3000/api/DAQ/Device/GetTableInfo
```Json
{
    "APIKEY":"_3qd1a3hfko5163ceb2ad174vq1u95yz3"
}
```