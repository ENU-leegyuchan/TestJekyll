---
layout: default
title: SendToBack
parent: 3.1.1 그래픽 다루기 API
grand_parent: 3.1 그래픽 스크립트 API (Lua)
grand_grand_parent: 3. enuSpace Meta API
---

# Lua API 

## SendToBack(Param1, Param2, ..., ParamN)

    - 입력받은 ID에 해당하는 객체들의 z축 위치를 맨 뒤로 조정합니다.

### Parameter (인자)

    - Param1 : string 객체 ID 1
    - Param2 : string 객체 ID 2
    - Param3 : string 객체 ID 3
    - ...
    - ParamN : string 객체 ID N

### Remark (주의사항)

    - 함수 실행 위치에서 접근 가능한 그래픽 객체만 조정할 수 있습니다. 

### 사용예시
```lua
function _onclick()
	SendToBack("ID_RECT1", "ID_CIRCLE", "ID_RECT2")
end
```

##