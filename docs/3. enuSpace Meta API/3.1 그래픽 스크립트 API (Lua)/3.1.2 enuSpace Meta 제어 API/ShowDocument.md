---
layout: default
title: ShowDocument
parent: 3.1.2 enuSpace Meta 제어 API
grand_parent: 3.1 그래픽 스크립트 API (Lua)
grand_grand_parent: 3. enuSpace Meta API
---

# Lua API 

## ShowDocument(Param1, [option]Param2)

    - 문서 파일을 Modal창에 호출하는 함수입니다.

<br>

### Parameter (인자)

    - Param1 : path
    - Param2 : [option] startPage Number
    - Param2 : [option] Action

### Return (반환값)

	- none

### Remark (주의사항)
    - 현) PDF 파일만 지원

### Example (함수사용 예시)

```lua
	function _onclick()
        ShowDocument("document/발표.pdf")
	end
```
```lua
	function _onclick()
        ShowDocument("document/발표.pdf", 3)
	end
```
```lua
	function _onclick()
        ShowDocument("document/발표.pdf", 'Next')
	end
```
```lua
	function _onclick()
        ShowDocument("document/발표.pdf", 'Prev')
	end
```