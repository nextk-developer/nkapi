---
layout: default
title: 이미지 등록
description:  이미지를 등록하면 검출된 객체와 비교해 매칭을 할 수 있습니다.
---

# Add or Update feature

## Request
```
POST /v3/va/add-or-update-feature

{
    "node_id": "53ba9bc997c72840",
    "feature_type": 0,
    "uuid": "12345",
    "user_id": "12345",
    "user_name": "apple",
    "user_age": 25,
    "identifier": 0,
    "gender" : 1,
    "feature_images" : ["/9j/4AAQSkZJRgABAQEAYABgAAD/2...."],
    "memo" : "memo"
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- |:----:|
| node_id | String | 컴퓨팅 노드 ID | O |
| uuid | String | 유저 UID (입력하지 않으면 서버에서 자동 할당) | X |
| feature_type | Enum | 특징 종류 (**[FeatureType](../common/models.html#featuretype)**) | O |
| user_id | String | 유저 ID | O |
| user_name | String | 이름 | O |
| user_age | Integer | 나이 | O |
| gender | Integer | 성별 (**[Gender](../common/models.html/#gender)**) | O |
| identifier | Integer | 인종 (**[Identifier](../common/models.html/#identifier)**) | O |
| feature_images | String[] | 이미지 정보 (Base64 Encoding) | O |
| memo | String | 메모 | X |

## Response

### SUCCESS
```
{
    "code": 0,
    "message": "",
    "uuid": "70697e9139e95a76"
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
| uuid | String | 유저 고유 ID | O |
| code | Enum | 응답 코드 (**[Error Code](../common/models.html#error-code)**) | O |
| message | String | 오류 메시지 | X |

# List feature

## Request
```
POST /v3/va/list-feature

{
    "node_id": "53ba9bc997c72840",
    "feature_type": 0
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- |:----:|
| node_id | String | 컴퓨팅 노드 ID | O |
| feature_type | Enum | 특징 종류 (**[FeatureType](../common/models.html#featuretype)**) | O |

## Response

### SUCCESS
```
{
    "code": 0,
    "message": "",
    "feature_list": [
        {
            "node_id": "53ba9bc997c72840",
            "feature_type": 0,
            "uuid": "12345",
            "user_id": "12345",
            "user_name": "apple",
            "user_age": 25,
            "identifier": 0,
            "gender" : 1,
            "feature_images" : ["/9j/4AAQSkZJRgABAQEAYABgAAD/2...."],
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
| feature_list | JsonObject[] | (**[이미지 정보](#feature)**) 리스트 | O |
| code | Enum | 응답 코드 (**[Error Code](../common/models.html#error-code)**) | O |
| message | String | 오류 메시지 | X |


### Feature

| Name | Type | Description | Required |
| :---- | :---- |:---- | :----:|
| node_id | String | 컴퓨팅 노드 ID | O |
| uuid | String | 유저 UID (입력하지 않으면 서버에서 자동 할당) | X |
| feature_type | Enum | 특징 종류 (**[FeatureType](../common/models.html#featuretype)**) | O |
| user_id | String | 유저 ID | O |
| user_name | String | 이름 | O |
| user_age | Integer | 나이 | O |
| gender | Integer | 성별 (**[Gender](../common/models.html/#gender)**) | O |
| identifier | Integer | 인종 (**[Identifier](../common/models.html/#identifier)**) | O |
| feature_images | String[] | 이미지 정보 (Base64 Encoding) | O |
| memo | String | 메모 | X |


# Remove feature

## Request
```
POST /v3/va/remove-feature

{
    "nodeId": "53ba9bc997c72840",
    "uuId": "70697e9139e95a76",
    "feature_type": 0
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- |:----:|
| nodeId | String | 컴퓨팅 노드 ID | O |
| uuId | String | 유저 UID | O |
| feature_type | Enum | 특징 종류 (**[FeatureType](../common/models.html#featuretype)**) | O |

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


# Matching feature

## Request
```
POST /v3/va/mathing-feature

{
    "node_id": "53ba9bc997c72840",
    "feature_type": 0,
    "uuid": "70697e9139e95a76",
    "feature_images" : ["/9j/4AAQSkZJRgABAQEAYABgAAD/2...."]
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- |:----:|
| node_id | String | 컴퓨팅 노드 ID | O |
| feature_type | Enum | 특징 종류 (**[FeatureType](../common/models.html#featuretype)**) | O |
| uuid | String | 유저 UID (입력하지 않으면 서버에서 자동 할당) | X |
| feature_images | String[] | 이미지 정보 (Base64 Encoding) | O |

## Response

### SUCCESS
```
{
    "code": 0,
    "message": "",
    "feature_type": 0,
    "uuid": "12345",
    "user_id": "12345",
    "user_name": "apple",
    "user_age": 25,
    "identifier": 0,
    "gender" : 1,
    "memo" : "memo"
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- | :----:|
| code | Enum | 응답 코드 (**[Error Code](../common/models.html#error-code)**) | O |
| message | String | 오류 메시지 | X |
| uuid | String | 유저 UID (입력하지 않으면 서버에서 자동 할당) | O |
| feature_type | Enum | 특징 종류 (**[FeatureType](../common/models.html#featuretype)**) | O |
| user_id | String | 유저 ID | O |
| user_name | String | 이름 | O |
| user_age | Integer | 나이 | O |
| gender | Enum | 객체 성별 (**[Gender](../common/models.html#gender)**) |
| identifier | Integer | 인종 (**[Identifier](../common/models.html/#identifier)**) | O |
| memo | String | 메모 | O |


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


#### FeatureType

| Enum | Value | Description |
| :---- | :---- |  :---- |
| Unknown | -1 | 알수없음 |
| Person | 0 | 사람 | 
| Face | 1 | 얼굴 |
| Vehicle | 2 | 차량 |


<br><br>

[뒤로](../../../../../index.html)