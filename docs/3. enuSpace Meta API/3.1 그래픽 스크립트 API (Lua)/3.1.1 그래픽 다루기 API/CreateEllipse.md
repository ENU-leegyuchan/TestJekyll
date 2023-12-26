---
layout: default
title: CreateEllipse
parent: 3.1.1 그래픽 다루기 API
grand_parent: 3.1 그래픽 스크립트 API (Lua)
grand_grand_parent: 3. enuSpace Meta API
---

# Lua API 

## CreateEllipse

    - Ellipse 객체를 생성하는 함수입니다.

### Parameter (인자)

    - Param1 : string 객체 ID
    - Param2 : float rx
    - Param3 : float ry
    - Param4 : float cx
    - Param5 : float cy
    - Param6 : float transX
    - Param7 : float transY

### Return (반환값)

	- Ellipse 객체
    - 객체 생성에 실패하였을 경우 0을 반환

### Remark (주의사항)

    - 타입에 맞는 인자 개수를 기입하지 않을 시 에러

### 사용예시
```lua
function _onclick()
    local obj = CreateEllipse("ID_ELLIPSE",100,50,200,200,0,0)
    obj.rx = 200
end
```
##