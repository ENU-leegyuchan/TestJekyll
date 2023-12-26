---
layout: default
title: GetHDF5Object
parent: 3.1.5 HDF5 데이터베이스 API
grand_parent: 3.1 그래픽 스크립트 API (Lua)
grand_grand_parent: 3. enuSpace Meta API
---

# Lua API 

## GetHDF5Object(Param1, Param2)

    - enuSpace Meta 서버의 프로젝트의 hdf5파일의 데이터셋을 요청하는 함수

<br>

### Parameter (인자)

    - Param1 : hdf5 filename
	- Param2 : hdf5 dataset pathname

### Return (반환값)

	- lua 테이블 객체를 반환합니다.

### Remark (주의사항)
    - 타입별 루아 테이블 객체의 구조
```lua
table
	shape
		rank
		dims
	type
		class
		base
	value
```

```lua
compound table
	shape
		rank
		dims
	type
		fields_size
		fields
			name
			class
			type
				base
	value
```

```lua
array table
	shape
		rank
		dims
	type
		dims
		rank
		base
			class
			base
	value
```

### Example (함수사용 예시)

```lua
	function _onclick()

		local HDF5data = GetHDF5Object(fileName, hierachy)
	    local dims1 = HDF5data.shape.dims[0]
	    local dims2 = HDF5data.shape.dims[1]
	    local strdata
	    for i = 0, dims1-1 do
	        for j = 0, dims2-1 do
	            if (i == 0 and j == 0) then
	              strdata = tostring(HDF5data.value[i][j])
	            else
	             strdata = string.format("%s,%s",strdata, tostring(HDF5data.value[i][j]))
	            end
	        end
	    end
	    data = strdata

	end
```