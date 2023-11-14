---
layout: default
title: 영상 분석 제어
description: 이 API를 이용하여 지정 채널에 대해 영상 분석을 시작하거나 중지할 수 있습니다.<br>또한 영상 분석 중 누적 된 데이터들을 초기화 할 수 있습니다.<br>예를 들어, ROI 영역의 검출객체 누적 카운팅 값을 초기화 할 수 있습니다.
---

# Control

영상 분석할 컴퓨팅 노드와 채널 리스트를 설정하여 분석 시작 / 중지 / 재시작 기능을 제공

## Request

```
POST /v2/va/control

# VA_START
{
    "nodeId": "a46147f4",
    "channelIds": ["19fa5688"],
    "operation": 0
}

# VA_STOP
{
    "nodeId": "a46147f4",
    "channelIds": ["19fa5688"],
    "operation": 1
}

# VA_RST
{
    "nodeId": "a46147f4",
    "channelIds" : ["X1ashF0t"],
    "operation" : 2
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- |:----: |
| nodeId | String | 컴퓨팅 노드 ID | O |
| channelIds | String[] | 채널 ID 리스트 | O |
| operation | Integer | 분석 제어 (**[Operations](../common/models.html/#operations)**) | O |

<br>

## Response

### SUCCESS
```
# VA_START 
{
    "sourceIp": "192.168.0.36",
    "sourcePort": 33300,
    "code": 0
}

# VA_STOP / VA_RESET
{
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
| :---- | :---- |:---- | :----: |
| sourceIp | String |  채널 메타데이터 서버 IP | X |
| sourcePort | Integer | 채널 메타데이터 서버 포트 | X |
| code | Enum | 응답 코드 (**[Error Code](../common/models.html#error-code)**) | O |
| message | String | 오류 메시지 | X |


<br><br>

[뒤로](../../../../../index.html)