---
layout: default
title: CreatePolyline
parent: 3.1.1 그래픽 다루기 API
grand_parent: 3.1 그래픽 스크립트 API (Lua)
grand_grand_parent: 3. enuSpace Meta API
---

# Lua API 

## CreatePolyline

    - Polyline 객체를 생성하는 함수입니다.

### Parameter (인자)

    - Param1 : string 객체 ID
    - Param2 : string d
    - Param3 : float transX
    - Param4 : float transY

### Return (반환값)

	- Polyline 객체
    - 객체 생성에 실패하였을 경우 0을 반환

### Remark (주의사항)

    - 타입에 맞는 인자 개수를 기입하지 않을 시 에러

### 사용예시
```lua
function _onclick()
    local obj = CreatePolyline("ID_POLYLINE", "0,0 50,50 100,0", 0,0)
    obj.translate_x = 200
end
```
##