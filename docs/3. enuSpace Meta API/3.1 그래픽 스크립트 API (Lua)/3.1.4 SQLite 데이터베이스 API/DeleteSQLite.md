---
layout: default
title: DeleteSQLite
parent: 3.1.4 SQLite 데이터베이스 API
grand_parent: 3.1 그래픽 스크립트 API (Lua)
grand_grand_parent: 3. enuSpace Meta API
---

# Lua API 

## DeleteSQLite(Param1, Param2)

    - enuSpace Meta 서버의 프로젝트의 저장된 SQLite파일의 데이터를 삭제하는 함수

### Parameter (인자)

    - Param1 : SQLite filename (path정보를 포함한 filename)
	- Param2 : SQLite query


### Return (반환값)

	- 정상적인 경우
	   서버측 프로젝트 내에 존재하는 파일명을 입력하고 delete쿼리를 제대로 입력했을때
	   정상적으로 반환된 json포맷 예시
		
```Json
{
	"Result" : "OK",
	"Msg" : "Success Delete."
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

	- 쿼리가 정상적으로 실행될 경우 데이터베이스 파일이 변환되기 때문에 새로고침이 됩니다.

### Example (함수사용 예시)

```lua
	function _onclick()
		local data = DeleteSQLite("test1.db", "DELETE FROM COMPANY WHERE ID=5;")
		local jsondcode = Json.decode(data)
		if(jsondcode.Result == "OK") then
			PrintMessage(jsondcode.Msg)
		else		-- jsondcode.Result == "FAIL"
			PrintMessage(jsondcode.Msg)
		end
	end
```