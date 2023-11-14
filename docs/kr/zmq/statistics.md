---
layout: default
title: 분석된 결과의 통계 수치 메타 포멧
description: 노드를 생성후 응답받은 TargetPort와 RpcPort의 조합으로 ZMQ의 PUB – SUB 방식으로 Subscribe하여 수신할 수 있습니다.<br>최대 7 일의 통계 데이터를 수신 할 수 있습니다.
---

# **Topic: statistics**

```
Sample
{
    "2023-11-14": [
        {
            "ChannelName": "NEXTK Channel 1",
            "ChannelUId": "27f2145494a4f20d",
            "DateTime": "2023-11-14",
            "Hours": [
                {
                    "Hour": 8,
                    "MinuteQuarters": [
                        {
                            "EventTypes": [
                                {
                                    "ClassIds": [
                                        {
                                            "ClassId": 116,
                                            "Count": 3
                                        },
                                        {
                                            "ClassId": 100,
                                            "Count": 12
                                        },
                                        {
                                            "ClassId": 125,
                                            "Count": 2
                                        },
                                        {
                                            "ClassId": 119,
                                            "Count": 3
                                        },
                                        {
                                            "ClassId": 134,
                                            "Count": 2
                                        },
                                        {
                                            "ClassId": 103,
                                            "Count": 1
                                        }
                                    ],
                                    "EventType": "Direction",
                                    "RoiNumber": 0,
                                    "RoiUId": "d3264aa033a7b2c2"
                                }
                            ],
                            "MinuteQuarter": 3
                        }
                    ]
                }
            ]
        },
        {
            "ChannelName": "NEXTK Channel",
            "ChannelUId": "b9126cb49314f61d",
            "DateTime": "2023-11-14",
            "Hours": [
                {
                    "Hour": 8,
                    "MinuteQuarters": [
                        {
                            "EventTypes": [
                                {
                                    "ClassIds": [
                                        {
                                            "ClassId": 0,
                                            "Count": 32
                                        }
                                    ],
                                    "EventType": "AllDetect",
                                    "RoiNumber": 0,
                                    "RoiUId": "f1d2b0cd38d7bd3d"
                                }
                            ],
                            "MinuteQuarter": 3
                        }
                    ]
                }
            ]
        }
    ]
}
```

### Event statistics dictionary

| Dictionary | Type | Description |
| :---- | :---- |:---- |
| Key | String | 날짜 (YYYY-MM-DD) |
| Value | JsonObject[] | **[채널별 통계 수치](#channel-event-statistics)**  |


### Channel event statistics

| Name | Type | Description |
| :---- | :---- |:---- |
| ChannelUId | String | 채널 ID |
| ChannelName | String | 채널 이름 |
| DateTime | String | 날짜 (YYYY-MM-DD) |
| Hours | JsonObject | **[시간별 통계](#hours-event-statistics)** |


### Hours event statistics

| Name | Type | Description |
| :---- | :---- |:---- |
| Hour | Integer | 시간 |
| MinuteQuarters | JsonObject[] | **[15분 기준 통계 수치](#minute-event-statistics)** |


### Minute event statistics

| Name | Type | Description |
| :---- | :---- |:---- |
| RoiUId | String | 관심 영역 ID |
| RoiNumber | Integer | 관심 영역 번호 (혹은 차로로 구분) |
| EventType | String | 이벤트 타입 (**[EventType](../api/v2/common/models.html/#eventtype)**) |
| ClassIds | JsonObject[] | **[이벤트 별 통계 수치](#classid-event-statistics)** |

### ClassId event statistics

| Name | Type | Description |
| :---- | :---- |:---- |
| ClassID | Integer | 채널 ID (**[ClassId](../api/v2/common/models.html/#classid)**) |
| Count | Integer | 개수 |

<br><br>

[뒤로](../../../index.html)