---
layout: default
title: 로그 조회 및 명령
description: 분석 서버의 로그를 조회 하거나 시스템 명령어를 전달 합니다.
---

# System log
## Request
```
POST /v2/system-log

{
    "nodeId" : "53ba9bc997c72840",
    "startTime" : "2023-06-21T00:00:00",
    "endTime" : "2023-06-21T23:59:59",
    "logType" : 127
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- | :----:|
| nodeId | String | 컴퓨팅 노드 ID | O |
| startTime | String | 로그의 시작 시간 [ISO-8601] | O |
| endTime | String | 로그의 끝 시간 [ISO-8601] | O |
| logType | Integer | 로그 타입 (**[LogType](../common/models.html#logtype)**) | O |

#### Remarkd
로그 타입을 | 연산으로 전달 가능합니다.

## Response

### SECCESS
```
{
    "code": 0
    "message": "SUCCESS"
    "logs" : [
        {'content': 'Turn ACTIVATE_MEDIA_SERVER', 'dateTime': '2023-06-21 09:53:02.158,', 'logType': 1}, 
        {'content': 'Immediately Run ACTIVATE_MEDIA_SERVER', 'dateTime': '2023-06-21 09:53:02.159,', 'logType': 1}, 
        {'content': 'RtspServer Try Listen', 'dateTime': '2023-06-21 09:53:02.159,', 'logType': 1}
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
| logs | JsonObject[] | 로그 정보 (**[SystemLog](#systemlog)**) | O |
| code | Enum | 응답 코드 (**[Error Code](../common/models.html#error-code)**) | O |
| message | String | 처리 메시지 | X |

### SystemLog

| Name | Type | Description | Required |
| :---- | :---- |:---- |:---- |
| content | String | 로그 내용 | O |
| dateTime | String | 로그 생성 시간 | O |
| logType | Integer | 로그 타입 (**[LogType](../common/models.html#logtype)**) | O |


# System
## Request
```
POST /v2/system

{
    "NodeId" : "53ba9bc997c72840",
    "CommandType" : 0,
    "Command" : "sudo reboot -f",
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- | :----:|
| NodeId | String | 컴퓨팅 노드 ID | O |
| CommandType | Enum | **[명령어 종류](#command-type)** | O |
| Command | String | 커스텀 명령어 | O |

### Command Type

| Value | Enum | Description |
| :---- | :---- |:---- |
| 0 | Custom | 커스텀 |
| 1 | Reboot | 재부팅 |
| 2| Restart | 재시작 |

## Response

### SECCESS
```
{
    "code": 0
    "message": "SUCCESS"
}
```

### REQUEST_TIMEOUT Or Something
```
{
    "code": 502,
    "message": "REQUEST_TIMEOUT"
}
```

<br><br>

[뒤로](../../../../../index.html)