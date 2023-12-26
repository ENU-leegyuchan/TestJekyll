---
layout: default
title: UpdateTable
parent: 3.3.1 디바이스 데이터 연동 API
grand_parent: 3.3 Server RESTful API
grand_grand_parent: 3. enuSpace Meta API
---

# Server API 

## UpdateTable(Param1)

    - 테이블의 여러 속성 값을 변경합니다.

### Protocol / Method
    - HTTP/POST
    - application/json

### Parameter (인자)

    - Param1 : Json 파일포맷

```Json
{
    "APIKEY":"APIKEY",
    "Table" : "변경 전 테이블명",
    "Data" : {
        "Table": "변경할 테이블명",
        "DBType": "변경할 DBType",
        "Access": "변경할 ACCESS",
        "AcquisitionType": "변경할 AcquisitionType",
        "Interval": "변경할 Acquisition interval",
        "DeviceIP": "변경할 DeviceIP",
        "SetUrl": "변경할 SetUrl",
        "GetUrl": "변경할 GetUrl"
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
    - AcquisitionType을 Slave에서 Master로 변경 시 Interval과 GetUrl이 필수로 있어야 합니다.

### Example (API 사용 예시)
    - HTTP/POST https://127.0.0.1:3000/api/DAQ/device/UpdateTable
```Json
{
    "APIKEY":"APIKEY",
    "Table" : "Table1",
    "Data" : {
        "Table": "Bright_Table",
        "DBType": "Druid",
        "Access": "Private",
        "AcquisitionType": "Master",
        "Interval": 5000,
        "DeviceIP": "192.168.0.1",
        "SetUrl": "",
        "GetUrl": "https://192.168.0.1/GetData"
    }
}
```