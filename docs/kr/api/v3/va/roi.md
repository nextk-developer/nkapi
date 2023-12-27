---
layout: default
title: 이벤트 ROI 설정
description: 개별 영상 내 이벤트 ROI(Region of interest) 설정 API입니다.<br>하나의 ROI에 하나의 이벤트를 설정 할 수 있으며, 세부 설정이 가능합니다.
---

# Add Or Update Roi
지정한 채널에 관심 영역을 정의하고, 관심 영역 내 분석 알고리즘을 설정합니다.

## Request
```
POST /v3/va/add-or-update-roi

{
    "node_id": "53ae8e84be6e03bb",
    "channel_id": "f8b5f54776f1a5de",
    "roi_id": "",
    "roi_name": null,
    "roi_type": 3,
    "evt_type": "AllDetect",
    "object_group": 0,
    "object_filter": [
        0,
        6,
        7,
        8,
        1002,
        1004,
        1001,
        1003,
        600,
        601,
        602
    ],
    "roi_points": [
        {
            "id": null,
            "roi_type": 3,
            "number": 0,
            "points": [
                {
                    "x": 0.29042553901672363,
                    "y": 0.164682537317276
                },
                {
                    "x": 0.6744681000709534,
                    "y": 0.164682537317276
                },
                {
                    "x": 0.6744681000709534,
                    "y": 0.6408730149269104
                },
                {
                    "x": 0.29042553901672363,
                    "y": 0.6408730149269104
                }
            ],
            "description": null
        }
    ],
    "min_max_size": {
        "min_detection_size": {
            "width": 0.01594387755102041,
            "height": 0.029714738510301108
        },
        "max_detection_size": {
            "width": 0.3840425610542297,
            "height": 0.47619047760963434
        }
    },
    "params": {
        "stay_time_sec": "0",
        "inside_roi_type": "0",
        "custom_reference_point": "",
        "intersection": "0",
        "thumbnail_ratio": "1, 1",
        "threshold": "0,0.5,6,0.5,7,0.5,8,0.5,1002,0.5,1004,0.5,1001,0.5,1003,0.5,600,0.5,601,0.5,602,0.5",
        "directional": "0, 0",
        "max_exit_time": "2"
    }
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- |:----: |
| node_id | String | 컴퓨팅 노드 ID | O |
| channel_id | String | 채널 ID | O |
| 상속 | JsonObject | ROI 정보(**[ROI](../common/models.html#roi)**) | O |


## Response
### SUCCESS
```
{
    "code": 0,
    "message": "SUCCESS",
    "roi": {
        "evt_type": "AllDetect",
        "min_max_size": {
            "max_detection_size": {
                "height": 0.47619047760963434,
                "width": 0.3840425610542297
            },
            "min_detection_size": {
                "height": 0.029714738510301108,
                "width": 0.01594387755102041
            }
        },
        "object_filter": [
            0,
            6,
            7,
            8,
            1002,
            1004,
            1001,
            1003,
            600,
            601,
            602
        ],
        "object_group": 0,
        "params": {
            "custom_reference_point": "",
            "directional": "0, 0",
            "inside_roi_type": "0",
            "intersection": "0",
            "max_exit_time": "2",
            "stay_time_sec": "0",
            "threshold": "0,0.5,6,0.5,7,0.5,8,0.5,1002,0.5,1004,0.5,1001,0.5,1003,0.5,600,0.5,601,0.5,602,0.5",
            "thumbnail_ratio": "1, 1"
        },
        "roi_id": "71b5cd3e0b3f238c",
        "roi_name": "",
        "roi_points": [
            {
                "description": "",
                "id": "25dfc4b83f48ec39",
                "number": 0,
                "points": [
                    {
                        "x": 0.29042553901672363,
                        "y": 0.164682537317276
                    },
                    {
                        "x": 0.6744681000709534,
                        "y": 0.164682537317276
                    },
                    {
                        "x": 0.6744681000709534,
                        "y": 0.6408730149269104
                    },
                    {
                        "x": 0.29042553901672363,
                        "y": 0.6408730149269104
                    }
                ],
                "roi_type": 3
            }
        ]
    }
}
```
### REQUEST_TIMEOUT
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
| roi | JsonObject | 관심영역 정보 | (**[ROI](../common/models.html#roi)**) |
| code | Enum | 응답 코드 (**[Error Code](../common/models.html#error-code)**) | O |
| message | String | 오류 메시지 | X |

# List Roi
지정한 채널에 ROI 항목을 조회합니다.

## Request
```
POST /v3/va/list-roi

{
    "node_id":"c6a45bc6",
    "channel_id":"svb90sc5"
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- |:----: |
| node_id | String | 컴퓨팅 노드 ID | O |
| channel_id | String | 채널 ID | O |


## Response

### SUCCESS
```
{
    "code": 0,
    "message": "SUCCESS",
    "roi_items": [
        {
            "evt_type": "FloodedOrSnowRoad",
            "min_max_size": {
                "max_detection_size": {
                    "height": 0.368254005908966,
                    "width": 0.13957449793815613
                },
                "min_detection_size": {
                    "height": 0.01594387755102041,
                    "width": 0.01594387755102041
                }
            },
            "object_filter": [
                100,
                102,
                103,
                116,
                118,
                119,
                123,
                125,
                126,
                129,
                130,
                131,
                132,
                133,
                134,
                135
            ],
            "object_group": 5,
            "params": {
                "custom_reference_point": "",
                "directional": "0, 0",
                "inside_roi_type": "0",
                "intersection": "0",
                "max_exit_time": "2",
                "stay_time_sec": "0",
                "threshold": "100,0.5,102,0.5,103,0.5,116,0.5,118,0.5,119,0.5,123,0.5,125,0.5,126,0.5,129,0.5,130,0.5,131,0.5,132,0.5,133,0.5,134,0.5,135,0.5",
                "thumbnail_ratio": "1, 1"
            },
            "roi_id": "58289e2110df822c",
            "roi_name": "",
            "roi_points": [
                {
                    "description": "1011",
                    "id": "396da75839c6763c",
                    "number": 0,
                    "points": [
                        {
                            "x": 0.24510636925697327,
                            "y": 0.5730158686637878
                        },
                        {
                            "x": 0.24510636925697327,
                            "y": 0.5730158686637878
                        },
                        {
                            "x": 0.2468085139989853,
                            "y": 0.9253968000411987
                        },
                        {
                            "x": 0.3846808671951294,
                            "y": 0.9333333373069763
                        },
                        {
                            "x": 0.373617023229599,
                            "y": 0.5650793313980103
                        }
                    ],
                    "roi_type": 2
                },
                {
                    "description": "1011",
                    "id": "8cacd3e2daa887b4",
                    "number": 1,
                    "points": [
                        {
                            "x": 0.3897872269153595,
                            "y": 0.5539682507514954
                        },
                        {
                            "x": 0.3897872269153595,
                            "y": 0.5539682507514954
                        },
                        {
                            "x": 0.4510638415813446,
                            "y": 0.8984126448631287
                        },
                        {
                            "x": 0.5651063919067383,
                            "y": 0.8158730268478394
                        },
                        {
                            "x": 0.47489359974861145,
                            "y": 0.5650793313980103
                        },
                        {
                            "x": 0.4740425646305084,
                            "y": 0.5603174567222595
                        }
                    ],
                    "roi_type": 2
                },
                {
                    "description": "1011",
                    "id": "7963a1b1e3d419cd",
                    "number": 2,
                    "points": [
                        {
                            "x": 0.5310638546943665,
                            "y": 0.541269838809967
                        },
                        {
                            "x": 0.5327659249305725,
                            "y": 0.5444444417953491
                        },
                        {
                            "x": 0.6348935961723328,
                            "y": 0.7936508059501648
                        },
                        {
                            "x": 0.7642553448677063,
                            "y": 0.7253968119621277
                        },
                        {
                            "x": 0.6527659296989441,
                            "y": 0.5206348896026611
                        }
                    ],
                    "roi_type": 2
                }
            ]
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
| :---- | :---- |:---- |:---- |
| code | Enum | 응답 코드 (**[Error Code](../common/models.html#error-code)**) | O |
| message | String | 오류 메시지 | X |
| roi_items | JsonObject[] | 관심 영역 정보 (**[Roi](../common/models.html#roi)**) | O |



# Remove roi
ROI 설정을 삭제합니다.

## Request
```
POST /v3/va/remove-roi

{
    "node_id": "c6a45bc6",
    "channel_id": "e84fcac4",
    "roi_ids": [
         "88e2a515"
    ]
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- |:----: |
| node_id | String | 컴퓨팅 노드 ID | O |
| channel_id | String | 채널 ID | O |
| roi_ids | String[] | 관심 영역 ID | O |


## Response

### SUCCESS
```
{
    "code": 0,
    "message" : ""
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
| message | String | 오류 메시지 | X |

# Update roi params

ROI 파라미터 설정을 수정합니다.

## Request

```
POST /v3/va/update-roi-params

{
    "node_id": "184fcb3c",
    "channel_id": "72040f36",
    "params": {
        "distance": "100"
    }
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- |:----: |
| node_id | String | 컴퓨팅 노드 ID | O |
| channel_id | String | 채널 ID | O |
| params | JsonObject | 파라미터 (**[Params](#params)**) | X |

## Response

### SUCCESS
```
{
    "code": 0
    "message" : ""
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
| message | String | 오류 메시지 | X |

<br><br>

### Params
참고, params내 항목이 설정이 잘못 되었을 경우 TIMEOUT 으로 Response 됩니다.

| Name | Type | Description | Required | Default | Sample | Events | 
| :---- | :---- |:---- |:----: |:----: |:----: | :----: |
| distance | String | 두 라인 사이의 거리 (단위: meter ) | O | - | 20 | Direction, Straight, LeftTurn, RightTrun, UTurn |
| thumbnail_ratio | String | 섬네일 객체 크기 지정 | X | 1, 1 | - | 모든 이벤트 |
| max_transition_time | String | 최초 존 전환(line crossing) 이후에 동일 객체에 대해 존 전환이 무시되는 최대 시간 (단위: seconds) | X | 2 | - | LineCrossing |
| stay_time_sec | String | ROI 진입 후 이벤트 지연 시간 | X | 0 | - | Polygon 객체 이벤트 (일부 제외) |
| inside_roi_type | String | [검출 박스의 ROI 진입 시작점](#insideroitype) | X | 0 | - | 모든 이벤트 |
| custom_reference_point | String | inside_roi_type가 CustomPoint일때 사용 (박스 좌상단 기준 + 지점)| X | 0.3(x), 0.2(y) | - | 모든 이벤트 |
| intersection | String | 검출 박스의 ROI 진입 퍼센트 | X | 0 ~ 100 | - | 모든 이벤트 |
| max_exit_time | String | 일시적으로 ROI를 벗어난 경우에 진입이 유지되는 시간 | X | 2 | - | LineEnter, LineCrossing, LineExit |
| more_than_count | String | 지정된 객체 수 이상이되면 이벤트 발생 | X | 1 | - | AbnormalObjectCount |
| threshold | String | 객체별 이벤트 민감도 (모델 민감도에 종속적)  | X | - | 0, 0.9, 1, 0.7 | 모든 이벤트 |
| directional | String | Roi내 진/출입 방향성 지정 (**[DirectionalType](#directionaltype)**)  | X | 0, 0 | - | Polygon 객체 이벤트 (일부 제외) |
| matching_score | String | 최소 인식 매칭 점수 | X | 0.99, 0.5 | - | NotWearingMask, MatchingFace |
| apply_mask_matching | String | 마스크 착용 매칭 기능 | X | False | - | NotWearingMask |
| stop_vx_vy | String | 객체의 정지 수치 범위 지정 | X | 15(int), 15(int) | - | QueueLength  |
| traffic_volume_dimension | String | 교통량 조사 단위 (시간 기준) | X | 24 | - | TrafficVolume  |

<!--
| debug | String | 개발사 전용 | X | false | - | 일부 이벤트 |
| travel_time | String | 객체 이동 시간 | X | 평균 이동 시간 | 2 | AbnormalCongestion |
| zone_width_ratio | String | 라인 이벤트 영역 범위 | X | 0.5 | - | LineEnter, LineCrossing, LineExit |
| hit_count | String | ROI내 이벤트가 유지되는 Frame 수 이상일때 이벤트 발생 | X | 0 | - | ElderlyPeople, NotWearingMask, TidyUpWorkbench |
| hit_percent | String | RGB 수치의 평균 | X | 90 | - | TidyUpWorkbench |
| hit_time_limit | String | hit_count가 유지되는 시간(단위 ms) | X | 3 | - | TidyUpWorkbench |
| psnr | String | 영상의 손실 정도  | X | 40 | - | TidyUpWorkbench |
-->


#### DirectionalType

| Enum | Value | Description |
| :---- | :---- |  :---- |
| None | 0 | 방향 X |
| Left_Top | 1 | ↖ |
| Top | 2 | ↑ | 
| Right_Top | 3 | ↗ |
| Right | 4 | → |
| Right_Bottom | 5 | ↘ | 
| Bottom | 6 | ↓ |
| Left_Bottom | 7 | ↙ |
| Left | 8 | ← |

#### InsideRoiType

| Enum | Value | Description |
| :---- | :---- |  :---- |
| CenterX_BottomY | 0 | 중앙 하단 |
| CenterX_CenterY | 1 | 중앙 | 
| LeftRightX_BottomY | 2 | 좌하단 + 우하단 |
| CustomPoint | 3 | 사용자 지정 |




<br><br>

[뒤로](../../../../../index.html)