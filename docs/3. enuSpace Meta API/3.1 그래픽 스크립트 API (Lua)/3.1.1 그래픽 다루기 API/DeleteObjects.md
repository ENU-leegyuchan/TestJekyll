---
layout: default
title: DeleteObjects
parent: 3.1.1 그래픽 다루기 API
grand_parent: 3.1 그래픽 스크립트 API (Lua)
grand_grand_parent: 3. enuSpace Meta API
---

# Lua API 

## DeleteObjects(Param1...)

    - 객체를 삭제하는 함수입니다.

### Parameter (인자)

    - Param1 : string 객체 ID

### Return (반환값)

	- none

### Remark (주의사항)

    - 파라미터 개수만큼 삭제를 수행합니다.
    - 에러 발생 시 로그에 에러메세지 기록 후 다음 파라미터로 넘어가서 마저 수행합니다.
    - 함수 실행 위치에서 접근 가능한 객체만 삭제할 수 있습니다.
    - 예를 들어, use객체 외부에서 use객체 내부의 객체에 대해서 삭제를 수행할 수 없습니다.

### 사용예시
```lua
function _onclick()
    DeleteObjects("ID_Rect", "ID_Path")
end
```
##