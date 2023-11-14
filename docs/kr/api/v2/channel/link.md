---
layout: default
title: 채널 링크 설정
description: 같은 곳을 보는 서로 다른 카메라를 연결하여 하나의 이벤트로 발생 합니다<br>일반적으로 RGB + IR 카메라의 조합으로 사용됩니다.
---

# Update channel link
서로 다른 채널을 연결 합니다.
<br>
(서브 채널이 메인 채널에 포함됩니다)

## Request
```
POST /v2/va/update-channel-link

{
    "nodeId": "e339d131d4a6bbc5",
    "mainChannelId": "channel1",
    "subChannelId": "channel2",
    "linkedType": "rtsp://211.198.128.30/vod/line1"
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- |:----: |
| nodeId | String | 컴퓨팅 노드 ID | O |
| mainChannelId | String | 메인 채널 ID | O |
| subChannelId | String | 서브 채널 별칭 | O |
| linkedType | Enum | (**[LinkedType](../common/models.html#linkedtype)**) | O |

## Response

### SUCCESS
```
{
    "channelId": "X1ashF0t",
    "sourceType": "NK-Edge",
    "mediaServerUrl": "rtsp://192.168.0.98:8554/live/main/e4075d5916fa3ef8",
    "mediaServerUrlSub": "",
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

# Update channel link points
채널 연결에 필요한 포인트를 설정합니다
<br>
이때 두 채널은 서로 같은 위치를 최소 4개 이상 설정 해야합니다.

## Request
```
POST /v2/va/update-channel-link-points

{
    "nodeId": "e339d131d4a6bbc5",
    "channelId": "channel1",
    "points": [
        {
            "x": 0,
            "y": 0
        },
        {
            "x": 1,
            "y": 0
        },
        {
            "x": 1,
            "y": 1
        },
        {
            "x": 0,
            "y": 1
        }
    ],
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- |:----: |
| nodeId | String | 컴퓨팅 노드 ID | O |
| channelId | String | 채널 ID | O |
| roiDots | JsonObject[] | ROI 라인 설정 (**[RoiDot](../common/models.html/#roi-dot)**) | O |

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



<br><br>

[뒤로](../../../../../index.html)