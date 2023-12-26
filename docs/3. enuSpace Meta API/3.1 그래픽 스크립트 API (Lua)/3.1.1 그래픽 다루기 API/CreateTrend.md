---
layout: default
title: CreateTrend
parent: 3.1.1 그래픽 다루기 API
grand_parent: 3.1 그래픽 스크립트 API (Lua)
grand_grand_parent: 3. enuSpace Meta API
---

# Lua API 

## CreateTrend

    - Trend 객체를 생성하는 함수입니다.

### Parameter (인자)

    - Param1 : string 객체 ID
    - param2 : string Trend Type
        1. 방사형 차트 (param3 : trend-radar)
        2. 히스토그램 차트 (param3 : trend-histogram)
        3. 실시간 차트 (param3 : trend-realtime)
        4. Countour 차트 (param3 : trend-contour-rect)
    - Param3 : float x
    - Param4 : float y
    - Param5 : float width
    - Param6 : float height
    - Param7 : float transX
    - Param8 : float transY

### Return (반환값)

	- Trend 객체
    - 객체 생성에 실패하였을 경우 0을 반환

### Remark (주의사항)

    - 타입에 맞는 인자 개수를 기입하지 않을 시 에러

### 사용예시
```lua
function _onclick()
    local obj = CreateTrend("ID_TEXT", "trend-histogram",0,0,500,500,0,0)
    obj.width = 300
end
```
##