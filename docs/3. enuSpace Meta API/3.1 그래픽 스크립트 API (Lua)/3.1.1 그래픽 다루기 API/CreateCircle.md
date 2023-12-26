---
layout: default
title: CreateCircle
parent: 3.1.1 그래픽 다루기 API
grand_parent: 3.1 그래픽 스크립트 API (Lua)
grand_grand_parent: 3. enuSpace Meta API
---

# Lua API 

## CreateCircle

    - Circle 객체를 생성하는 함수입니다.

### Parameter (인자)

    - Param1 : string 객체 ID
    - Param2 : float r
    - Param3 : float cx
    - Param4 : float cy
    - Param5 : float transX
    - Param6 : float transY

### Return (반환값)

	- Circle 객체
    - 객체 생성에 실패하였을 경우 0을 반환

### Remark (주의사항)

    - 타입에 맞는 인자 개수를 기입하지 않을 시 에러

### 사용예시
```lua
function _onclick()
    local obj = CreateCircle("ID_CIRCLE",100,200,200,0,0)
    obj.r = 400
end
```
##