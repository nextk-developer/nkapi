---
layout: default
title: 영상 반출
description: 서버에 저장되어 있는 영상을 반출 합니다.
---


## Request
```
POST /v3/record/export

{
    "node_id": "53ae8e84be6e03bb",
    "channel_id": "53ae8e84be6e03bb",
    "start_time": "2023-06-09T00:00:00",
    "end_time": "2023-06-09T23:59:59",
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- |:----: |
| node_id | String | 컴퓨팅 노드 ID | O |
| start_time | String | 영상 재생 시작시간 [ISO-8601] | O |
| end_time | String | 영상 재생 끝나는시간 [ISO-8601] | O |


## Response
### SUCCESS
```
{
    "code": 0,
    "message": "SUCCESS",
    "ftp_user": "nextk",
    "ftp_pass": "enter2424",
    "download_urls": [ "root/pass/1.mp4", "root/pass/2.mp4", "root/pass/3.mp4"]
}
```


| Name | Type | Description | Required |
| :---- | :---- |:---- |:----: |
| code | Enum | 응답 코드 (**[Error Code](../common/models.html#error-code)**) | O |
| ftp_user | String | 로그인 아이디 | O |
| ftp_pass | String | 로그인 페스워드 | O |
| download_urls | String Array | 다운 로드 받아야 할 영상 리스트 | O |


### REQUEST_TIMEOUT or Somethings
```
{
    "code": 502,
    "message": "REQUEST_TIMEOUT"
}
```
### NOT_FOUND_COMPUTING_NODE
```
{
    "code": 503,
    "message": "NOT_FOUND_COMPUTING_NODE"
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- |:----: |
| code | Enum | 응답 코드 (**[Error Code](../common/models.html#error-code)**) | O |
| message | String | 오류 메시지 | X |

<br><br>

[뒤로](../../../../../index.html)