---
layout: default
title: CreateTable
parent: 3.3.1 디바이스 데이터 연동 API
grand_parent: 3.3 Server RESTful API
grand_grand_parent: 3. enuSpace Meta API
---

# Server API 

## CreateTable(Param1)

    - Table 생성을 요청하는 API입니다.

### Protocol / Method
    - HTTP/POST
    - application/json

### Parameter (인자)

    - Param1 : Json 파일포맷

```Json
{
    "Id" : "SystemID",
    "Table" : "테이블명",
    "Access" : "접근권한(Public, Private)",
    "AcquisitionType" : "데이터 취득 방식(Master, Slave)",
    "DeviceIP" : "디바이스의 IP",
    "Interval" : "데이터 취득 간격(ms)",
    "GetUrl" : "데이터 취득 url",
    "SetUrl" : "디바이스에 값 할당을 위한 url",
    "DBType" : "사용할 DB 종류(Druid)",
    "TagInfoList" : [
        {
            "Tag" : "태그명1",
            "Type" : "태그 데이터 타입(string, double, int)",
            "Description" : "태그 설명",
            "IOType" : "IoT 태그의 input, output 종류",
            "Value" : "초기값"
        },
        {
            "Tag" : "태그명2",
            "Type" : "태그 데이터 타입(string, double, int)",
            "Description" : "태그 설명",
            "IOType" : "IoT 태그의 input, output 종류",
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
    Acquisition Type 
    Master : DB가 Device에 접근 할 수 있는 상태 
    Slave : DB가 Device에 접근 할 수 없는 상태
    - Master일 때에는 Interval 주기마다 GetUrl 을 통해 데이터를 취득, SetUrl을 통해 제어
    - Slave일 때에는 Device가 직접 DB로 값을 적재하고 제어

    Interval은 ms(밀리세컨드)단위로, 1000 = 1초 이다. 
    너무 작은 단위의 수를 입력하면 원활한 적재가 이루어지지 않을 수 있다.

### Example (API 사용 예시)
    - HTTP/POST https://127.0.0.1:3000/api/DAQ/device/CreateTable
```Json
{  
    "ID": "123",
    "Table": "Table1",
    "DBType": "Druid",
    "Access": "Public",
    "AcquisitionType": "Master",
    "DeviceIP": "2000",
    "GetUrl":"https://192.168.0.224:5000/GetDeviceValues",
    "SetUrl": "https://192.168.0.224:5000/SetDeviceValues",
    "TagInfoList": [
        {
            "Type": "int",
            "Description": "LED",
            "Tag": "LED_1",
            "IOType": "Output",
            "Value" : "0"
        },
        {
            "Type": "double",
            "Description": "temp",
            "Tag": "Temp_2",
            "IOType": "Input",
            "Value" : "36.5"
        }
    ]
}
```