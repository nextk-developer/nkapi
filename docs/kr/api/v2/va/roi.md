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
    "description": "",
    "stayTime": 0,
    "numberOf": 0,
    "roiNumber": 0,
    "feature": 0,
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
| description | String | 설명 | X |
| stayTime | Integer | [not supported] ~~발생 지연 시간~~ | X |
| numberOf | Integer | [not supported] ~~최소 발생 객체수 조건~~ | X |
| eventType | Integer | 이벤트 종류 (**[EventType](../common/models.html/#eventtype)**)| O |
| feature | Integer | [not supported] ~~ROI 감지 (**[ROI Feature](../common/models.html/#roi-feature)**)~~ | O |
| roiDots | JsonObject[] | ROI 라인 설정 (**[RoiDot](../common/models.html/#roi-dot)**) | O |
| eventFilter | JsonObject | 검출 객체 사이즈 필터 (**[EventFilter](../common/models.html/#event-filter)**)| O |
| objectTypes | Integer[] | 검출 객체 필터 (**[ClassId](../common/models.html/#classid)**)| O |
| roiNumber | Integer | 차선 번호 | X |
| params | JsonObject | 파라미터 | X |

#### Remakrs
* params
  - distance: 미터 단위 

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
            "description": "",
            "stayTime": 0,
            "numberOf": 0,
            "eventType": "AllDetect",
            "roiType": 2,
            "feature": 0,
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
| description | String | 설명 | X |
| stayTime | Integer | [not supported] ~~발생 지연 시간~~ | X |
| numberOf | Integer | [not supported] ~~최소 발생 객체수 조건~~ | X |
| eventType | Integer | 이벤트 종류 (**[EventType](../common/models.html/#eventtype)**)| O |
| feature | Integer | [not supported] ~~ROI 감지 (**[ROI Feature](../common/models.html/#roi-feature)**)~~ | O |
| roiDots | JsonObject[] | ROI 라인 설정 (**[RoiDot](../common/models.html/#roi-dot)**) | O |
| eventFilter | JsonObject | 검출 객체 사이즈 필터 (**[EventFilter](../common/models.html/#event-filter)**)| O |
| objectTypes | Integer[] | 검출 객체 필터 (**[ClassId](../common/models.html/#classid)**)| O |
| roiNumber | Integer | 차선 번호 | X |
| params | JsonObject | 파라미터 | X |

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
    "description": "",
    "stayTime": 0,
    "numberOf": 0,
    "roiNumber": 0,
    "feature": 0,
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
| description | String | 설명 | X |
| stayTime | Integer | [not supported] ~~발생 지연 시간~~ | X |
| numberOf | Integer | [not supported] ~~최소 발생 객체수 조건~~ | X |
| eventType | Integer | 이벤트 종류 (**[EventType](../common/models.html/#eventtype)**)| O |
| feature | Integer | [not supported] ~~ROI 감지 (**[ROI Feature](../common/models.html/#roi-feature)**)~~ | O |
| roiDots | JsonObject[] | ROI 라인 설정 (**[RoiDot](../common/models.html/#roi-dot)**) | O |
| eventFilter | JsonObject | 검출 객체 사이즈 필터 (**[EventFilter](../common/models.html/#event-filter)**)| O |
| objectTypes | Integer[] | 검출 객체 필터 (**[ClassId](../common/models.html/#classid)**)| O |
| roiNumber | Integer | 차선 번호 | X |
| params | JsonObject | 파라미터 | X |


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

<br><br>

[뒤로](../../../../../index.html)