---
layout: default
title: 얼굴 등록
description:  얼굴을 등록하면 검출된 객체의 얼굴과 비교해 매칭을 할 수 있습니다.
---

# Register face db

## Request
```
POST /v2/va/register-facedb

{
    "nodeId": "53ba9bc997c72840",
    "uuId": "12345",
    "userId": "12345",
    "userName": "apple",
    "userAge": 25,
    "gender" : 1,
    "identifier": 0,
    "faceImages" : ["/9j/4AAQSkZJRgABAQEAYABgAAD/2...."],
    "memo" : "memo"
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- |:----:|
| nodeId | String | 컴퓨팅 노드 ID | O |
| uuId | String | 유저 UID (입력하지 않으면 서버에서 자동 할당) | X |
| userId | String | 유저 ID | O |
| userName | String | 이름 | O |
| userAge | Integer | 나이 | O |
| gender | Integer | 성별 (**[Gender](../common/models.html/#gender)**) | O |
| identifier | Integer | 인종 (**[Identifier](../common/models.html/#identifier)**) | O |
| faceImages | String[] | 얼굴 이미지 정보 (Base64 Encoding) | O |
| memo | String | 메모 | X |

## Response

### SUCCESS
```
{
    "code": 0,
    "message": "",
    "uuId": "70697e9139e95a76"
}
```

### REQUEST_TIMEOUT Or Something
```
{
    "code": 502,
    "message": "REQUEST_TIMEOUT"
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- | :----:|
| uuId | String | 유저 고유 ID | O |
| code | Enum | 응답 코드 (**[Error Code](../common/models.html#error-code)**) | O |
| message | String | 오류 메시지 | X |

# List face db

## Request
```
POST /v2/va/list-facedb

{
    "nodeId": "53ba9bc997c72840"          
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- |:----:|
| nodeId | String | 컴퓨팅 노드 ID | O |

## Response

### SUCCESS
```
{
    "code": 0,
    "message": "",
    "faceDBs": [
        {
            "nodeId": "53ba9bc997c72840",
            "uuId": "12345",
            "userId": "12345",
            "userName": "apple",
            "userAge": 25,
            "identifier": 0,
            "gender" : 1,
            "faceImages" : ["/9j/4AAQSkZJRgABAQEAYABgAAD/2...."],
            "memo" : "memo"
        }
    ]
}
```

### REQUEST_TIMEOUT Or Something
```
{
    "code": 502,
    "message": "REQUEST_TIMEOUT"
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- | :----:|
| faceDBs | JsonObject[] | [얼굴 이미지 정보](#face-db) 리스트 | O |
| code | Enum | 응답 코드 (**[Error Code](../common/models.html#error-code)**) | O |
| message | String | 오류 메시지 | X |


### Face DB

| Name | Type | Description | Required |
| :---- | :---- |:---- | :----:|
| nodeId | String | 컴퓨팅 노드 ID | O |
| uuId | String | 유저 UID (입력하지 않으면 서버에서 자동 할당) | O |
| userId | String | 유저 ID | O |
| userName | String | 이름 | O |
| userAge | Integer | 나이 | O |
| gender | Enum | 성별 (**[Gender](../common/models.html/#gender)**) | O |
| identifier | Enum | 인종 (**[Identifier](../common/models.html/#identifier)**) | O |
| faceImages | String[] | 얼굴 이미지 정보 (Base64 Encoding) | O |
| memo | String | 메모 | X |


# Remove face db

## Request
```
POST /v2/va/remove-facedb

{
    "nodeId": "53ba9bc997c72840",
    "uuId": "70697e9139e95a76"         
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- |:----:|
| nodeId | String | 컴퓨팅 노드 ID | O |
| uuId | String | 유저 UID | O |

## Response

### SUCCESS
```
{
    "code": 0,
    "message": ""
}
```

### REQUEST_TIMEOUT Or Something
```
{
    "code": 502,
    "message": "REQUEST_TIMEOUT"
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- | :----:|
| code | Enum | 응답 코드 (**[Error Code](../common/models.html#error-code)**) | O |
| message | String | 오류 메시지 | X |


<br><br>

[뒤로](../../../../../index.html)