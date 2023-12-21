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
            "camera_name": "NEXTK Channel 1",
            "camera_id": "27f2145494a4f20d",
            "date_time": "2023-11-14",
            "hours": [
                {
                    "hour": 8,
                    "minute_quarters": [
                        {
                            "event_types": [
                                {
                                    "class_ids": [
                                        {
                                            "class_id": 116,
                                            "count": 3
                                        },
                                        {
                                            "class_id": 100,
                                            "count": 12
                                        },
                                        {
                                            "class_id": 125,
                                            "count": 2
                                        },
                                        {
                                            "class_id": 119,
                                            "count": 3
                                        },
                                        {
                                            "class_id": 134,
                                            "count": 2
                                        },
                                        {
                                            "class_id": 103,
                                            "count": 1
                                        }
                                    ],
                                    "evt_type": "Direction",
                                    "number": 0,
                                    "roi_id": "d3264aa033a7b2c2"
                                }
                            ],
                            "minute_quarter": 3
                        }
                    ]
                }
            ]
        },
        {
            "camera_name": "NEXTK Channel",
            "camera_id": "b9126cb49314f61d",
            "date_time": "2023-11-14",
            "hours": [
                {
                    "hour": 8,
                    "minute_quarters": [
                        {
                            "event_types": [
                                {
                                    "class_ids": [
                                        {
                                            "class_id": 0,
                                            "count": 32
                                        }
                                    ],
                                    "evt_type": "AllDetect",
                                    "number": 0,
                                    "roi_id": "f1d2b0cd38d7bd3d"
                                }
                            ],
                            "minute_quarter": 3
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
| camera_id | String | 채널 ID |
| camera_name | String | 채널 이름 |
| date_time | String | 날짜 (YYYY-MM-DD) |
| hours | JsonObject | **[시간별 통계](#hours-event-statistics)** |


### hours event statistics

| Name | Type | Description |
| :---- | :---- |:---- |
| hour | Integer | 시간 |
| minute_quarters | JsonObject[] | **[15분 기준 통계 수치](#minute-event-statistics)** |


### Minute event statistics

| Name | Type | Description |
| :---- | :---- |:---- |
| roi_id | String | 관심 영역 ID |
| number | Integer | 관심 영역 번호 (혹은 차로로 구분) |
| evt_type | String | 이벤트 타입 (**[EventType](../api/v3/common/models.html#evt_type)**) |
| class_ids | JsonObject[] | **[이벤트 별 통계 수치](#class_id-event-statistics)** |

### class_id event statistics

| Name | Type | Description |
| :---- | :---- |:---- |
| class_id | Enum | 채널 ID (**[ClassId](../api/v3/common/models.html#class_id)**) |
| count | Integer | 개수 |

<br><br>

[뒤로](../../../index.html)