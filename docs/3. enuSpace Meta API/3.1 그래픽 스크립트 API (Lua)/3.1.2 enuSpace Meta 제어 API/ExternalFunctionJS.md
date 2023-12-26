---
layout: default
title: ExternalFunctionJS
parent: 3.1.2 enuSpace Meta 제어 API
grand_parent: 3.1 그래픽 스크립트 API (Lua)
grand_grand_parent: 3. enuSpace Meta API
---

# Lua API 

## ExternalFunctionJS(Param1)

    - 루아 스크립트함수에서 외부의 JS함수를 호출하는 함수입니다.
    - enuSpaceInterface.js 파일의 Call_ExternalFunctionJS(strParam)함수를 호출합니다.

<br>

### Parameter (인자)

    - Param1 : 사용자 정의 파라미터 입력

### Return (반환값)
	- none

### Remark (주의사항)
    - none

### Example (함수사용 예시)

```lua
function _onclick()
	value = ExternalFunctionJS(strParam)
end
```

```js
function Call_ExternalFunctionJS(strParam)
{
    var URL = "";               // 사용자 서버주소를 지정
    var data = "";              // 사용자 파라미터 지정
    var RequestURL = UTF8ToString(URL);
    var RequestData = UTF8ToString(Data);
    var xmlHttp = new XMLHttpRequest();
    xmlHttp.onreadystatechange=function()
    {
        if (xmlHttp.readyState==4 && xmlHttp.status==200)
        {       
            var msg = xmlHttp.responseText;

            // msg 내용
            // {"TagName":"Test2_Tag0","Value":"0.265387"},{"TagName":"Test2_Tag1","Value":"0.340363"}
            User_SetGlobalValues(msg);
        }
    };
   
    xmlHttp.open("POST",RequestURL,true);   
    xmlHttp.setRequestHeader("Content-Type","text/plain");
    xmlHttp.send(RequestData); 
}
```