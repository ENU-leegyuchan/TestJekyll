---
layout: default
title: CreateObject
parent: 3.1.1 그래픽 다루기 API
grand_parent: 3.1 그래픽 스크립트 API (Lua)
grand_grand_parent: 3. enuSpace Meta API
---

# Lua API 

## CreateObject(Param1, Param2, Param3...)

    - 그래픽 객체를 생성하는 함수입니다.

### Parameter (인자)

    - Param1 : string 객체 타입 
    - Param2 : string 객체 ID
    - Param3 : 객체에 따른 가변인자

### 가변인자 / 사용예시

<details><summary><strong>Rect</strong></summary>

### 가변인자
    param3 : float x
    param4 : float y
    param5 : float width
    param6 : float height
    param7 : float transX
    param8 : float transY

### 사용예시
```lua
function _onclick()
    local obj = CreateObject("rect","ID_RECT",0,0,200,200,0,0)
    obj.width = 300
end
```

</details>

<details><summary><strong>Line</strong></summary>

### 가변인자
    param3 : float x1
    param4 : float y1
    param5 : float x2
    param6 : float y2
    param7 : float transX
    param8 : float transY

### 사용예시
```lua
function _onclick()
    local obj = CreateObject("line","ID_LINE",0,0,200,200,0,0)
    obj.x1 = 100
end
```

</details>

<details><summary><strong>Circle</strong></summary>

### 가변인자
    param3 : float r
    param4 : float cx
    param5 : float cy
    param6 : float transX
    param7 : float transY

### 사용예시
```lua
function _onclick()
    local obj = CreateObject("circle","ID_CIRCLE",100,200,200,0,0)
    obj.r = 400
end
```

</details>

<details><summary><strong>Ellipse</strong></summary>

### 가변인자
    param3 : float rx
    param4 : float ry
    param5 : float cx
    param6 : float cy
    param7 : float transX
    param8 : float transY

### 사용예시
```lua
function _onclick()
    local obj = CreateObject("ellipse","ID_ELLIPSE",100,50,200,200,0,0)
    obj.rx = 200
end
```

</details>

<details><summary><strong>Path</strong></summary>

### 가변인자
    param3 : string d
    param4 : float transX
    param5 : float transY

### 사용예시
```lua
function _onclick()
    local obj = CreateObject("path","ID_PATH", "M0,0 L100,100 L0,100 Z", 0,0)
    obj.d = "M100,0 L100,100 L0,0"
end
```

</details>

<details><summary><strong>Polygon</strong></summary>

### 가변인자
    param3 : string points
    param4 : float transX
    param5 : float transY

### 사용예시
```lua
function _onclick()
    local obj = CreateObject("polygon","ID_POLYGON", "0,0 50,50 100,0", 0,0)
    obj.translate_x = 200
end
```

</details>

<details><summary><strong>Polyline</strong></summary>

### 가변인자
    param3 : string points
    param4 : float transX
    param5 : float transY

### 사용예시
```lua
function _onclick()
    local obj = CreateObject("polyline","ID_POLYLINE", "0,0 50,50 100,0", 0,0)
    obj.translate_x = 200
end
```

</details>

<details><summary><strong>Image</strong></summary>

### 가변인자
    param3 : string href
    param4 : float x
    param5 : float y
    param6 : float width
    param7 : float height
    param8 : float transX
    param9 : float transY

### 사용예시
```lua
-- 외부 링크 이미지
function _onclick()
    local obj = CreateObject("image","ID_IMAGE", "https://expnuni.github.io/enuspace_doc/assets/enuspace.png", 0,0,200,200,0,0)
    obj.href = "/resource/back.png"
end

-- 프로젝트 내부 resource 폴더의 이미지
function _onclick()
    local obj = CreateObject("image","ID_IMAGE", "/resource/back.png", 0,0,200,200,0,0)
end
```

</details>

<details><summary><strong>Text</strong></summary>

### 가변인자
    param3 : string text
    param4 : float x
    param5 : float y
    param6 : float dx
    param7 : float dy
    param8 : float transX
    param8 : float transY

### 사용예시
```lua
function _onclick()
    local obj = CreateObject("text","ID_TEXT", "Hello, World!",0,0,0,0,0,0)
    obj.text = "Hello, World!!!"
end
```

</details>

<details><summary><strong>Use</strong></summary>

### 가변인자
    param3 : string href (ex : #symbolName)
    param4 : float transX
    param5 : float transY

### 사용예시
```lua
function _onclick()
    local obj = CreateObject("use","ID_USE", "#symbolName",0,0)
    obj.translate_x = 200
end
```

</details>

<details><summary><strong>Trend</strong></summary>

### 가변인자
    param3 : string Trend Type
        1. 방사형 차트 (param3 : trend-radar)
        2. 히스토그램 차트 (param3 : trend-histogram)
        3. 실시간 차트 (param3 : trend-realtime)
        4. Countour 차트 (param3 : trend-contour-rect)
    param4 : float x
    param5 : float y
    param6 : float width
    param7 : float height
    param8 : float transX
    param9 : float transY

### 사용예시
```lua
function _onclick()
    local obj = CreateObject("pg-trend","ID_TREND", "trend-histogram",0,0,500,500,0,0)
    obj.translate_x = 200
end
```

</details>

---

### Return (반환값)

	- 타입에 따른 객체
    - 객체 생성에 실패하였을 경우 0을 반환

### Remark (주의사항)

    - 타입에 맞는 인자 개수를 기입하지 않을 시 에러

##