---
layout: default
title: SelectSQLite
parent: 3.1.4 SQLite 데이터베이스 API
grand_parent: 3.1 그래픽 스크립트 API (Lua)
grand_grand_parent: 3. enuSpace Meta API
---

# Lua API 

## SelectSQLite(Param1, Param2)

    - enuSpace Meta 서버의 프로젝트의 저장된 SQLite파일의 데이터를 조회하는 함수

### Parameter (인자)

    - Param1 : SQLite filename (path정보를 포함한 filename)
	- Param2 : SQLite query


### Return (반환값)

	- 정상적인 경우
	   서버측 프로젝트 내에 존재하는 파일명을 입력하고 update쿼리를 제대로 입력했을때
	   정상적으로 반환된 json포맷 예시

```Json
{
	"Result" : "OK",
	"Msg" : "Success Select.",
	"Data" :
	[
		{
			"ADDRESS" : "California",
			"AGE" : "32",
			"ID" : "1",
			"NAME" : "Paul",
			"SALARY" : "30000.0"
		},
		{
			"ADDRESS" : "Texas",
			"AGE" : "25",
			"ID" : "2",
			"NAME" : "Allen",
			"SALARY" : "15000.0"
		}
	]
}
```

### Remark (주의사항)

    - 비정상적인 경우
	   1. 서버측 프로젝트 내에 존재하지 않는 파일명을 입력했을때
	   2. 쿼리를 잘못 입력했을때
	   비정상적으로 반환된 json포맷 예시

```Json
1.	{
		"Result" : "FAIL",
		"Msg" : "Could not find db file."
	}

2.	{
		"Result" : "FAIL",
		"Msg" : "error message."
	}
```

### Example (함수사용 예시)

```lua
	function _onclick()
		local data = SelectSQLite("test1.db", "SELECT * FROM COMPANY")
		local jsondcode = Json.decode(data)
		if (jsondcode.Result == "OK") then
			for i=1, #jsondcode.Data do
				name = jsondcode.Data[i].NAME
				age = jsondcode.Data[i].AGE
				address = jsondcode.Data[i].ADDRESS
				salary = jsondcode.Data[i].SALARY
				PrintMessage(name)
			end
		else		-- jsondcode.Result == "FAIL"
			PrintMessage(jsondcode.Msg)
		end
	end
```