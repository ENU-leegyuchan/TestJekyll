---
layout: default
title: SetTaskviewCycle
parent: 3.1.2 enuSpace Meta 제어 API
grand_parent: 3.1 그래픽 스크립트 API (Lua)
grand_grand_parent: 3. enuSpace Meta API
---

# Lua API 

## SetTaskviewCycle(Param1)

    - Lua Event인 OnTaskview event의 초당 수행 횟수를 설정합니다.

<br>

### Parameter (인자)

    - Param1 : 초당 수행 횟수


### Return (반환값)

	- none

### Remark (주의사항)
    - 기본값은 24이며, 최소값은 1, 최대값은 24입니다.
    - Param이 1보다 작을 경우 1, 24보다 클 경우 24로 설정됩니다.
    - 주어진 환경에 따라, 현재 task가 느릴 경우 설정한 수행 횟수보다 느릴 수 있습니다.

### Example (함수사용 예시)

```lua
	function _onclick()
      SetTaskviewCycle(12)
	end
```
