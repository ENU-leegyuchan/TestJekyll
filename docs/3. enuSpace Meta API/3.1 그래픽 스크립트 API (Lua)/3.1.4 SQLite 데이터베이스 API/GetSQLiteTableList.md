---
layout: default
title: GetSQLiteTableList
parent: 3.1.4 SQLite 데이터베이스 API
grand_parent: 3.1 그래픽 스크립트 API (Lua)
grand_grand_parent: 3. enuSpace Meta API
---

# Lua API 

## GetSQLiteTableList(Param1)

    - enuSpace Meta 서버의 프로젝트의 저장된 SQLite파일의 테이블리스트를 조회하는 함수

### Parameter (인자)

    - Param1 : SQLite filename (path정보를 포함한 filename)


### Return (반환값)

	- 정상적인 경우
	   서버측 프로젝트 내에 존재하는 파일명을 입력했을때
	   정상적으로 반환된 json포맷 예시

```Json
{
	"Result" : "OK",
	"Msg" : "Success TableList.",
	"Data" :
	[
		{
			"content" : "COMPANY",
			"type" : "Table"
		}
		{
			"content" : "COMPANY2",
			"type" : "Table"
		}
	]
}
```

### Remark (주의사항)

    - 비정상적인 경우
	   서버측 프로젝트 내에 존재하지 않는 파일명을 입력했을때
	   비정상적으로 반환된 json포맷 예시

```Json
{
	"Result" : "FAIL",
	"Msg" : "Could not find db file."
}
```

### Example (함수사용 예시)

```lua
	function _onclick()
		local data = GetSQLiteTableList("test1.db")
		local jsondcode = Json.decode(data)
		if (jsondcode.Result == "OK") then
			for i=1, #jsondcode.Data do
				content = jsondcode.Data[i].content
				PrintMessage(content)
			end
		else		-- jsondcode.Result == "FAIL"
			PrintMessage(jsondcode.Msg)
		end
	end
```