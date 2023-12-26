---
layout: default
title: GetHDF5JsonCallback
parent: 3.1.5 HDF5 데이터베이스 API
grand_parent: 3.1 그래픽 스크립트 API (Lua)
grand_grand_parent: 3. enuSpace Meta API
---

# Lua API 

## GetHDF5JsonCallback(Param1, Param2, Param3)

    - enuSpace Meta 서버의 프로젝트의 hdf5파일의 Json 포맷의 데이터셋을 비동기 요청하는 함수

<br>

### Parameter (인자)

    - Param1 : hdf5 filename
	- Param2 : hdf5 dataset pathname
	- Param3 : callback function name


### Return (반환값)

	- json 파일 포맷의 문자열 데이터

### Remark (주의사항)
    - Param3을 빈칸으로 기입 시 요청하지 않음
	- callback으로 실행시켜 줄 함수는 GetHDF5JsonCallback 함수가 실행된 객체에 존재해야 함
	- callback 함수는 비동기 요청 후 응답 메세지를 받을 파라미터가 필요함에 따라 파라미터를 하나만 사용해야 함

### Example (함수사용 예시)

```lua
	function _onclick()
		GetHDF5Json(＂hdf5/Test.h5＂, ＂ROOT/TEST＂, "_userfunction")
	end

	function _userfunction(msg)
		jsondcode = Json.decode(msg)
		dimsi = jsondcode.shape.dims[1]
		PrintMessage(tostring(dimsi))
	end

	func
```