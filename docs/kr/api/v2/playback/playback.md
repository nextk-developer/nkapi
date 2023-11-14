---
layout: default
title: 플레이백
description:  저장되어있는 영상에 한하여 Playback을 할 수 있습니다.<br>레코딩 설정이 선행 되어야 합니다.
---

# Playback

원하는 시간대의 영상을 불러옵니다.
<br>
현재 지원되는 프로토콜은 RTSP입니다.

## Request
```
POST /v2/va/playback

{
    "nodeId": "813ee7995af2e8cd",
    "channelId": "d08eae12e807e0db",
    "startTime": "2023-06-09T00:00:00",
    "endTime": "2023-06-09T23:59:59",
    "includeMeta": false,
    "protocol": 0
}
```

| Name | Type | Description | Required |
| :---- | :---- | :---- |:----: |
| nodeId | String | 컴퓨팅 노드 ID | O |
| channelId | String | 채널 ID | O |
| startTime | String | 영상 재생 시작시간 (startTime ~ endTime 범위안의 영상 재생) | O |
| endTime | String | 영상 재생 끝나는시간 (startTime ~ endTime 범위안의 영상 재생) | O |
| includeMeta | bool | [not Supported] 메타 데이터 포함 여부 | O |
| protocol | Enum | 프로토콜 (**[Playback Protocol](../common/models.html#playback-protocol)**)| O |

## Response

###  SUCCESS
```
{
    "code" : 0,
    "mediaUrl": "rtsp://192.168.0.98:8554/playback/8ca28b54ec156338",
    "metaUrl": ""
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
| mediaUrl | String | 영상 재생 URL | O |
| metaUrl | String | [not Supported] 메타 URL | X |



<br><br>

[뒤로](../../../../../index.html)