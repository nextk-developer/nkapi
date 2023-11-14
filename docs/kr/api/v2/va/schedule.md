---
layout: default
title: 분석 스케쥴 설정
description:  채널 단위 영상 분석 설정을 할 수 있습니다.
---

# VA Schedule
지정한 시간과 요일에 영상 분석을 실시합니다.


## Request
```
POST /v2/va/va-schedule

{
    "nodeId": "3f16f31ecc13647d",
    "channelId": "5939a61ad39c0c37",
    "schedule": [
        [1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1],
        [1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1],
        [1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1],
        [1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1],
        [1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1],
        [1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1],
        [1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1]
    ],
    "except": [
      "01.01","03.01","05.05","06.06","08.15","10.03","10.09","12.25"
    ]
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- |:----: |
| nodeId | String | 컴퓨팅 노드 ID | O |
| channelId | String | 채널 ID | O |
| schedule | Integer[][] | [(일 ~ 토)][(0 ~ 23)] = 분석 여부 | O |
| except | String[] | 분석 제외 날짜 | X |

<br>

## Response
```
// SUCCESS
{
    "code": 0,
    "message" : ""
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- |:----: |
| code | Enum | 응답 코드 (**[Error Code](../common/models.html#error-code)**) | O |
| message | String | 오류 메시지 | X |

<br><br>

[뒤로](../../../../../index.html)