---
layout: default
title: 컴퓨팅 노드 설정
description:  실시간 영상 분석을 수행할 컴퓨팅 노드를 관리하는 API입니다.<br>컴퓨팅 노드는 AI-Edge 프로세스를 논리적으로 지칭합니다.
---

# Create computing node
분석 서버(노드)를 등록합니다.

## Request
```
POST /v2/va/create-computing-node

{
  "host": "192.168.0.39",
  "nodeName": "TEST_SYSTEM_PC",
  "license": "NKAI_IP_MAC_servercnt_chcnt"
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- |:----:|
| host | String | 호스트주소 | O |
| nodeName | String | 노드 닉네임 | O |
| license | String | 암호화된 라이선스 값 (**[Licese](#license)**)  | O |

## Response

### Success
```
{
  "nodeId": "350d8934",
  "productVersion": "1.0.8.9",
  "releaseDate": "2023.06.01",
  "code": 0
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
| nodeId | String | 컴퓨팅 노드 ID | O |
| productVersion | String | 제품 버전| O |
| releaseDate | String | 제품 릴리즈 날짜 | O |
| code | Enum | 응답 코드 (**[Error Code](../common/models.html#error-code)**) | O |
| message | String | 처리 메시지 | X |

<br>

# Get computing node
분석 서버(노드) 정보를 조회합니다.

## Request
```
POST /v2/va/get-computing-node 
{
}
```
## Response

### Success
```
{
  "node": 
  {
    "nodeId": "e339d131d4a6bbc5", 
    "httpHost": "192.168.0.98", 
    "httpPort": 8880, 
    "rpcHost": "192.168.0.98", 
    "rpcPort": 5556,
    "nodeName": "Computing Node", 
    "releaseDate": "2023.06.01", 
    "productVersion": "1.0.8.9", 
    "description": "", 
    "licenseValidity": True, 
    "licenseExpired": "2023.06.01", 
    "functions": [ 0 ]
  },
  "code": 0
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
| :---- | :---- |:---- | :----|
| nodeId | String | 컴퓨팅 노드 ID | O |
| httpHost | String | http 호스트 | O |
| httpPort | Integer | http 포트 | O |
| rpcHost | String | 메타 전송 호스트 | O |
| rpcPort | Integer | 메타 전송 포트 | O |
| nodeName | String | 컴퓨팅 노드 이름| O |
| releaseDate | String | 제품 릴리즈 날짜 | O |
| productVersion | String | 제품 버전 | O |
| description | String | 제품 설명 | X |
| licenseValidity | Boolean | 라이센스 유효 여부 | X |
| licenseExpired | String | 라이센스 만료 기간 | X |
| functions | Integer[] | 사용가능 기능 | X |
| code | Enum | 응답 코드 (**[Error Code](../common/models.html#error-code)**) | O |
| message | String | 처리 메시지 | X |


# Update computing node
분석 서버(노드)를 수정합니다.

## Request
```
POST /v2/va/update-computing-node

{
    "nodeId": "14f502f2",
    "nodeName": "TEST_NODE",
    "license" : "NKAI_IP_MAC_servercnt_chcnt"
}
```


| Name | Type | Description | Required |
| :---- | :---- |:---- |:---- |
| nodeId | String | 노드 ID | O |
| nodeName | String | 노드 닉네임 | O |
| license | String | 암호화된 라이선스 값 (**[Licese](#license)**)  | O |

<br>

## Response

### Success
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
| :---- | :---- |:---- |:----: |
| code | Enum | 응답 코드 (**[Error Code](../common/models.html#error-code)**) | O |
| message | String | 처리 메시지 | X |

# Remove computing node
분석 서버(노드)를 삭제 합니다.

## Request
```
POST /v2/va/remove-computing-node

{
    "nodeId": "4945bb32"
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- |:----: |
| nodeId | String | 노드 ID | O |

<br>

## Response

### SUCCESS
```
{
    "nodeId": "4945bb32",
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
| :---- | :---- |:---- |:----: |
| nodeId | String | 노드 ID | O |
| code | Enum | 응답 코드 (**[Error Code](../common/models.html#error-code)**) | O |
| message | String | 처리 메시지 | X |

<br>

## License 

| Name | Description |
| :---- |:---- |
| license | 암호화 방식에 대한 내용은 사내 개발자와 협의 필요 | 

<br><br>

[뒤로](../../../../../index.html)