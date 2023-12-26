---
layout: default
title: GetNodeByID
parent: 3.1.1 그래픽 다루기 API
grand_parent: 3.1 그래픽 스크립트 API (Lua)
grand_grand_parent: 3. enuSpace Meta API
---

# Lua API 

## GetNodeByID(Param1)

    - 기존에 생성되어있는 객체 중 입력받은 ID와 같은 ID를 가진 객체를 가져옵니다.

### Parameter (인자)

    - Param1 : 객체 ID

### Return (반환값)

	- 타입에 따른 객체
    - 객체를 가져오는데 실패하였을 경우 0을 반환

### Remark (주의사항)

    - 함수 실행 위치에서 접근 가능한 객체만 가져올 수 있습니다. 
    - 예를 들어, use객체 외부에서 use객체 내부의 객체에 대해서 접근할 수 없습니다.
    - Trend의 component를 가져오려면 TrendID.ComponentID의 형태로 가져옵니다.

### 사용예시
```lua
function _onclick()
	local getNode = GetNodeByID("ID_RECT")
    getNode.width = 333
end

function _onclick()
	local getComponent = GetNodeByID("ID_TREND.Legend")
    getComponent.width = 200
end
```

##