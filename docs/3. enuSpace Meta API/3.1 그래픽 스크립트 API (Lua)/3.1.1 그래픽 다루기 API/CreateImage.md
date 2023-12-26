---
layout: default
title: CreateImage
parent: 3.1.1 그래픽 다루기 API
grand_parent: 3.1 그래픽 스크립트 API (Lua)
grand_grand_parent: 3. enuSpace Meta API
---

# Lua API 

## CreateImage

    - Image 객체를 생성하는 함수입니다.

### Parameter (인자)

    - Param1 : string 객체 ID 
    - Param2 : string href
    - Param3 : float x
    - Param4 : float y
    - Param5 : float width
    - Param6 : float height
    - Param7 : float transX
    - Param8 : float transY

### Return (반환값)

	- Image 객체
    - 객체 생성에 실패하였을 경우 0을 반환

### Remark (주의사항)

    - 타입에 맞는 인자 개수를 기입하지 않을 시 에러

### 사용예시
```lua
-- 외부 링크 이미지
function _onclick()
    local obj = CreateImage("ID_IMAGE", "https://expnuni.github.io/enuspace_doc/assets/enuspace.png", 0,0,200,200,0,0)
    obj.href = "/resource/back.png"
end

-- 프로젝트 내부 resource 폴더의 이미지
function _onclick()
    local obj = CreateImage("ID_IMAGE", "/resource/back.png", 0,0,200,200,0,0)
end
```
##