---
layout: default
title: CreateLine
parent: 3.1.1 그래픽 다루기 API
grand_parent: 3.1 그래픽 스크립트 API (Lua)
grand_grand_parent: 3. enuSpace Meta API
---

# Lua API 

## CreateLine

    - Line 객체를 생성하는 함수입니다.

### Parameter (인자)

    - Param1 : string 객체 ID
    - Param2 : float x1
    - Param3 : float y1
    - Param4 : float x2
    - Param5 : float y2
    - Param6 : float transX
    - Param7 : float transY

### Return (반환값)

	- Line 객체
    - 객체 생성에 실패하였을 경우 0을 반환

### Remark (주의사항)

    - 타입에 맞는 인자 개수를 기입하지 않을 시 에러

### 사용예시
```lua
function _onclick()
    local obj = CreateLine("ID_LINE",0,0,200,200,0,0)
    obj.x1 = 100
end
```
##