---
layout: default
title: 이벤트 ROI 설정
description: 개별 영상 내 이벤트 ROI(Region of interest) 설정 API입니다.<br>하나의 ROI에 하나의 이벤트를 설정 할 수 있으며, 세부 설정이 가능합니다.
---

# Create roi
지정한 채널에 관심 영역을 정의하고, 관심 영역 내 분석 알고리즘을 설정합니다.

## Request
```
POST /v2/va/create-roi

{
    "nodeId": "184fcb3c",
    "channelId": "72040f36",
    "roiId": "",
    "name": "ROI_NAME",
    "roiType": 2,
    "eventType": "Loitering",
    "roiNumber": 0,
    "roiDots": [
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
    "objectTypes": [
        0
    ],
    "eventFilter": {
        "minDetectSize": 1,
        "maxDetectSize": 100,
        "objectsTarget": [
            0
        ]
    },
    "params": {
        "distance": "100"
    }
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- |:----: |
| nodeId | String | 컴퓨팅 노드 ID | O |
| channelId | String | 채널 ID | O |
| name | String | ROI 이름 | O |
| roiType | Integer | ROI 타입(**[DrawingType](../common/models.html/#roi-drawing-type)**) | O |
| eventType | Integer | 이벤트 종류 (**[EventType](../common/models.html/#eventtype)**)| O |
| roiDots | JsonObject[] | ROI 라인 설정 (**[RoiDot](../common/models.html/#roi-dot)**) | O |
| eventFilter | JsonObject | 검출 객체 사이즈 필터 (**[EventFilter](../common/models.html/#event-filter)**)| O |
| objectTypes | Integer[] | 검출 객체 필터 (**[ClassId](../common/models.html/#classid)**)| O |
| roiNumber | Integer | 차선 번호 | X |
| params | JsonObject | 파라미터 (**[Params](#params)**) | X |


## Response
### SUCCESS
```
{
    "roiId": "88e2a515",
    "code": 0,
    "message": ""
}
```
### REQUEST_TIMEOUT
```
{
    "roiId": "",
    "code": 502,
    "message": "REQUEST_TIMEOUT"
}
```
### NOT_FOUND_COMPUTING_NODE
```
{
    "roiId": "",
    "code": 503,
    "message": "NOT_FOUND_COMPUTING_NODE"
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- |:----: |
| roiId | String | 관심 영역 ID | O |
| code | Enum | 응답 코드 (**[Error Code](../common/models.html#error-code)**) | O |
| message | String | 오류 메시지 | X |

# List Roi
지정한 채널에 ROI 항목을 조회합니다.

## Request
```
POST /v2/va/list-roi

{
    "nodeId":"c6a45bc6",
    "channelId":"svb90sc5"
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- |:----: |
| nodeId | String | 컴퓨팅 노드 ID | O |
| channelId | String | 채널 ID | O |


## Response

### SUCCESS
```
{
    "rois": [
        {
            "roiId": "3aa26e5979b14636",
            "name": "test name",
            "eventType": "AllDetect",
            "roiType": 2,
            "roiDots": [
                {
                    "x": 0.4,
                    "y": 0.1
                },
                {
                    "x": 0.9,
                    "y": 0.1
                },
                {
                    "x": 0.9,
                    "y": 0.6
                },
                {
                    "x": 0.4,
                    "y": 0.6
                }
            ],
            "EventFilter": {
                "minDetectSize": 0,
                "maxDetectSize": 0,
                "objectsTarget": [
                    0
                ]
            },
            "objectTypes": [
                0
            ],
            "roiNumber": 0,
            "params": {
                "distance": ""
            }
        }
    ],
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
| :---- | :---- |:---- |:---- |
| nodeId | String | 컴퓨팅 노드 ID | O |
| channelId | String | 채널 ID | O |
| name | String | ROI 이름 | O |
| roiType | Integer | ROI 타입 (**[DrawingType](../common/models.html/#roi-drawing-type)**) | O |
| eventType | Integer | 이벤트 종류 (**[EventType](../common/models.html/#eventtype)**)| O |
| roiDots | JsonObject[] | ROI 라인 설정 (**[RoiDot](../common/models.html/#roi-dot)**) | O |
| eventFilter | JsonObject | 검출 객체 사이즈 필터 (**[EventFilter](../common/models.html/#event-filter)**)| O |
| objectTypes | Integer[] | 검출 객체 필터 (**[ClassId](../common/models.html/#classid)**)| O |
| roiNumber | Integer | 차선 번호 | X |
| params | JsonObject | 파라미터 (**[Params](#params)**) | X |

# Update roi

ROI 설정을 수정합니다.

## Request

```
POST /v2/va/update-roi

{
    "nodeId": "184fcb3c",
    "channelId": "72040f36",
    "roiId": "",
    "name": "ROI_NAME",
    "roiType": 2,
    "eventType": "Loitering",
    "roiNumber": 0,
    "roiDots": [
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
    "objectTypes": [
        0
    ],
    "eventFilter": {
        "minDetectSize": 1,
        "maxDetectSize": 100,
        "objectsTarget": [
            0
        ]
    },
    "params": {
        "distance": "100"
    }
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- |:----: |
| nodeId | String | 컴퓨팅 노드 ID | O |
| channelId | String | 채널 ID | O |
| name | String | ROI 이름 | O |
| roiType | Integer | ROI 타입 (**[DrawingType](../common/models.html/#roi-drawing-type)**) | O |
| eventType | Integer | 이벤트 종류 (**[EventType](../common/models.html/#eventtype)**)| O |
| roiDots | JsonObject[] | ROI 라인 설정 (**[RoiDot](../common/models.html/#roi-dot)**) | O |
| eventFilter | JsonObject | 검출 객체 사이즈 필터 (**[EventFilter](../common/models.html/#event-filter)**)| O |
| objectTypes | Integer[] | 검출 객체 필터 (**[ClassId](../common/models.html/#classid)**)| O |
| roiNumber | Integer | 차선 번호 | X |
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
| roiId | String | 관심 영역 ID | O |
| code | Enum | 응답 코드 (**[Error Code](../common/models.html#error-code)**) | O |
| message | String | 오류 메시지 | X |

# Remove roi
ROI 설정을 삭제합니다.

## Request
```
POST /v2/va/remove-roi

{
    "nodeId": "c6a45bc6",
    "channelId": "e84fcac4",
    "roiIds": [
         "88e2a515"
    ]
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- |:----: |
| nodeId | String | 컴퓨팅 노드 ID | O |
| channelId | String | 채널 ID | O |
| roiId | String[] | 관심 영역 ID | O |


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
POST /v2/va/update-roi-params

{
    "nodeId": "184fcb3c",
    "channelId": "72040f36",
    "params": {
        "distance": "100"
    }
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- |:----: |
| nodeId | String | 컴퓨팅 노드 ID | O |
| channelId | String | 채널 ID | O |
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
| roiId | String | 관심 영역 ID | O |
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
| stop_vx_vy | String | 객체의 정지 수치 범위 지정 | X | 15, 15 | - | QueueLength  |


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