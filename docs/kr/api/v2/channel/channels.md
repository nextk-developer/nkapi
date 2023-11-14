---
layout: default
title: 채널 설정
description: 채널은 1개의 비디오에 대한 정보이며, 영상분석을 수행하는 단위입니다.
---

# Register channel
비디오 분석을 수행할 채널을 등록합니다.

## Request
```
POST /v2/va/register-channel

{
    "nodeId": "e339d131d4a6bbc5",
    "channelId": "",
    "channelName": "NEXTK Channel",
    "inputUrl": "rtsp://211.198.128.30/vod/line1",
    "inputUrlSub": "rtsp://211.198.128.30/vod/line1",
    "inputType": 0,
    "groupName": "NEXTK Group",
    "description": "경기도 용인시 기흥구 서천로201번길 11 725호",
    "autoTimeout": True
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- |:----: |
| nodeId | String | 컴퓨팅 노드 ID | O |
| channelId | String | 채널 ID (ID 미등록시 자동 생성)| X |
| channelName | String | 채널 별칭 | X |
| inputUrl | String | 입력 영상 URI (RTSP 주소, 파일 경로) | O |
| inputUrlSub | String | 입력 영상 SUB URI (RTSP 주소, 파일 경로) | X |
| inputType | Integer | [deprecated] ~~입력 비디오 타입 (**[InputType](../common/models.html#inputtype)**)~~ | O |
| groupName | String | 채널 그룹 별칭 | O |
| description | String | 채널 상세 정보 | X |
| autoTimeout | bool | 자동 시간 초과 | X |

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

| Name | Type | Description | Required |
| :---- | :---- |:---- |:----: |
| channelId | String | 채널 ID | O |
| code | Enum | 응답 코드 (**[Error Code](../common/models.html#error-code)**) | O |
| mediaServerUrl | String | 미디어 서버 URL | O |
| mediaServerUrlSub | String |  미디어 서버 SUB URL| X |
| message | String | 오류 메시지 | X |
| ~~sourceType~~ | ~~String~~ | [deprecated] ~~Channel GRPC 타입~~ | X |

<br>

<!-- ### Remarks

#### nodeId
채널의 입력 영상에 대해 비디오 분석을 수행 할 컴퓨팅 노드의 ID 입니다. 비디오 분석을 수행하기 위해서는 최소 1개의 컴퓨팅 노드가 필요합니다. -->

<!-- #### siblings

동일한 목표지점을 촬영하는 채널인 경우, sibling 관계가 될 수 있습니다. 예를 들어, 같은 위치에서 같은 목표지점을 촬영하도록 일반카메라와 열화상카메라 CCTV가 각각 설치 된 경우입니다. 이 때, 두 CCTV 영상들의 분석결과는 서로 상관관계가 있으므로, 이것을 응용 앱에서 활용하기 위해 본 파라메터를 이용하여 sibling 관계를 관리할 수 있습니다. -->


# List channel
전체 채널 상세정보를 조회합니다.

## Request
```
POST /v2/va/list-channel 
{
    "nodeId" : "53ba9bc997c72840"
}
```

## Response
``` 
{
    "channels": [
        {   
            "channelId": "e24f07a9a1aaf64d", 
            "channelName": "NEXTK Channel", 
            "description": "경기도 용인시 기흥구 서천로201번길 11 725호", 
            "frameHeight": 1080, 
            "frameWidth": 1920, 
            "group": "NEXTK Group", 
            "inputType": 0,
            "inputUrl": "rtsp://211.198.128.30/vod/line1", 
            "inputUrlSub": "rtsp://211.198.128.30/vod/line1", 
            "link": 
                {
                    "channelUid": "a18cc3a4f58634b8", 
                    "linkedType": 1, 
                    "points": [
                        {
                            "x": 0.0,
                            "y": 0.0
                        },
                        {
                            "x": 0.84,
                            "y": 0.0
                        },
                        {
                            "x": 0.84,
                            "y": 0.22
                        },
                        {
                            "x": 0.0,
                            "y": 0.5
                        }
                    ]
                }, 
            "mediaServerPort": 8554, 
            "mediaServerUrl": "rtsp://192.168.0.98:8554/live/main/e24f07a9a1aaf64d", 
            "mediaServerUrlSub": "", 
            "rpcPort": 5556
        }, 
        {   
            "channelId": "a18cc3a4f58634b8", 
            "channelName": "NEXTK Channel 1", 
            "description": "경기도 용인시 기흥구 서천로201번길 11 725호", 
            "frameHeight": 1080, 
            "frameWidth": 1920, 
            "group": "NEXTK Group", 
            "inputType": 0,
            "inputUrl": "rtsp://211.198.128.30/vod/line1", 
            "inputUrlSub": "rtsp://211.198.128.30/vod/line1", 
            "link": 
                {
                    "channelUid": "e24f07a9a1aaf64d", 
                    "linkedType": 1, 
                    "points": [
                        {
                            "x": 0.0,
                            "y": 0.0
                        },
                        {
                            "x": 0.84,
                            "y": 0.0
                        },
                        {
                            "x": 0.84,
                            "y": 0.22
                        },
                        {
                            "x": 0.0,
                            "y": 0.5
                        }
                    ]
                }, 
            "mediaServerPort": 8554, 
            "mediaServerUrl": "rtsp://192.168.0.98:8554/live/main/a18cc3a4f58634b8", 
            "mediaServerUrlSub": "", 
            "rpcPort": 5556
        }
    ], 
    "code": 0
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- |:----: |
| channelId | String | 채널 ID | O |
| channelName | String | 채널 이름 | O |
| description | String | 채널 상세 정보 | O |
| frameHeight | Integer | 영상 높이 | O |
| frameWidth | Integer | 영상 넓이 | O |
| group | String | 채널 그룹 별칭 | O |
| inputType | Integer | [deprecated] ~~입력 비디오 타입 (**[InputType](../common/models.html#inputtype)**)~~ | O |
| inputUrl | String | 입력 비디오 URI(RTSP 주소 또는 로컬파일 경로) | O |
| inputUrlSub | String | 입력 비디오 SUB URI(RTSP 주소 또는 로컬파일 경로) | O |
| channelUid | String | 링크 채널 ID | O |
| linkedType | Enum | **[LinkType](../common/models.html#linktype)**  | O |
| points | JsonObject[] | ROI 라인 설정 (**[RoiDot](../common/models.html#roi-dot)**) | O |
| mediaServerPort | Integer | 미디어 서버 포트 | O |
| mediaServerUrl | String | 미디어 서버 URL | O |
| mediaServerUrlSub | String | 미디어 서버 SUB URL | O |
| rpcPort | Integer | rpc 서버 포트 | O |
| sourceType | String | [deprecated] ~~Channel GRPC 타입~~ | X |

<br><br>

# Update channel
채널의 정보를 수정합니다.

## Request

```
POST /v2/va/update-channel

{
    "nodeId" : "5c009c52"
    "groupName": "NEXTK Group",
    "channelId": "6a694f0e",
    "channelName": "NEXTK Channel",
    "inputUrl": "rtsp://211.198.128.30/vod/line1",
    "inputUrlSub": "rtsp://211.198.128.30/vod/line1",
    "inputType": 0,
    "description": "경기도 용인시 기흥구 서천로201번길 11 725호",
    "autoTimeout": false
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- |:----: |
| nodeId | String | 컴퓨팅 노드 ID | O |
| groupName | String | 채널 그룹 별칭 | X |
| channelId | String | 채널 ID | O |
| channelName | String | 채널 별칭 | X |
| inputUrl | String | 입력 비디오 URI(RTSP 주소 또는 로컬파일 경로) | O |
| inputUrlSub | String | 입력 비디오 SUB URI(RTSP 주소 또는 로컬파일 경로) | X |
| inputType | Integer | [deprecated] ~~입력 비디오 타입 (**[InputType](../common/models.html#inputtype)**)~~ | O |
| description | String | 채널 상세 정보 | X |
| autoTimeout | bool | 자동 시간 초과  | X |

<br>

## Response

### SUCCESS 
```
{
    "mediaServerUrl": "rtsp://192.168.0.98:8554/live/main/32900814071418e",
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

| Name | Type | Description | Required |
| :---- | :---- |:---- |:----: |
| channelId | String | 채널 ID | X |
| mediaServerUrl | String | 미디어 서버 URL | O |
| mediaServerUrlSub | String | 미디어 서버 SUB URL | X |
| code | Enum | 응답 코드 (**[Error Code](../common/models.html#error-code)**) | O |
| message | String | 오류 메시지 | X |
| ~~sourceType~~ | ~~String~~ | [deprecated] ~~Channel GRPC 타입~~ | X |

# Remove channel
채널의 정보를 삭제합니다.

## Request
```
POST /v2/va/remove-channel

{
    "nodeId" : "5c009c52",
    "channelId": "6a694f0e"
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
    "channelId": "6a694f0e",
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
| :---- | :---- |:---- |:----: |
| channelId | String | 채널 ID | O |
| code | Enum | 응답 코드 (**[Error Code](../common/models.html#error-code)**) | O |
| message | String | 오류 메시지 | X |

### Remarks
비디오 분석이 실행 중인 채널은 분석 실행을 중단 후에 삭제하는 것을 권고합니다.

# [Not Supported] Calibrate (수동)

해당 채널의 영상 기준 캘리브레이션 값을 적용하는 기능을 지원합니다.
* 추가 객체 실제사이즈,거리 및 추적 성능 개선이 가능합니다.

## Request
```
POST /v2/va/callibrate

{
    "nodeId" : "5c009c52",
    "channelId": "6a694f0e",
    "calibration" : 
    {
        "focalLengthX" : 0.5,
        "focalLengthY" : 0.2,
        "principalX" : 0.04,
        "principalY" : 0.01,
        "fov" : 1.0,
        "imageWorldX" : 0.3,
        "imageWorldY" : 0.1,
        "imageWorldZ" : 0.5,
        "cameraPanDegree" : 90.0,
        "cameraTiltDegree" : 10.0,
        "cameraHorizontalAngle" : 0.0
    }
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- |:----: |
| nodeId | String | 컴퓨팅 노드 ID | O |
| channelId | String | 채널 ID | O |
| calibration | JsonObject | 캘리브레이션 값(**[Caliration](../common/models.html#calibration)**)| O |

## Response

### SUCCESS
```
{
    "channelId": "6a694f0e",
    "code" : 0
}
```

### REQUEST_TIMEOUT Or Something
```
{
    "code": 502,
    "message": "REQUEST_TIMEOUT"
}
```

| Name | Type | Description |
| :---- | :---- |:---- |
| channelId | String | 채널 ID | O |
| code | Enum | 응답 코드 (**[Error Code](../common/models.html#error-code)**) | O |
| message | String | 오류 메시지 |

# [Not Supported] Calibrate (자동)

해당 채널의 영상 좌표 정보를 획득하여, 좌표 왜곡 보정 기능을 지원합니다.
* 캘리브레이션 지원 라이센스를 발급 받아야 사용 가능합니다.
* 추가 객체 실제사이즈,거리 및 추적 성능 개선이 가능합니다.

## Request
```
POST /v2/va/callibrate

{
    "nodeId" : "5c009c52",
    "channelId": "6a694f0e",
    "firstLine" : 
    {
        "startPointX" : 0.3,
        "startPointY" : 0.1,
        "endPointX" : 0.35,
        "endPointY" : 0.6,
    },
    "secondLine" : 
    {
        "startPointX" : 0.7,
        "startPointY" : 0.3,
        "endPointX" : 0.76,
        "endPointY" : 0.72,
    }
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- |:----: |
| nodeId | string | 컴퓨팅 노드 ID | O |
| channelId | String | 채널 ID | O |
| firstLine | JsonObject | 왜곡 보정을 위한 첫번째 직선 (**[Line](#line)**)| O |
| secondLine | JsonObject | 왜곡 보정을 위한 두번째 직선 (**[Line](#line)**)| O |

### Line

| Name | Type | Description | Required |
| :---- | :---- |:---- |:---- |
| startPointX | double | 시작 위치 X좌표 | O |
| startPointY | double | 시작 위치 X좌표 | O |
| endPointX | double | 종료 위치 X좌표 | O |
| endPointY | double | 종료 위치 X좌표 | O |

<br>

## Response

### SUCCESS
```
{
    "channelId": "6a694f0e",
    "code" : 0
}
```

### REQUEST_TIMEOUT Or Something
```
{
    "code": 502,
    "message": "REQUEST_TIMEOUT"
}
```

| Name | Type | Description |
| :---- | :---- |:---- |
| channelId | String | 채널 ID | O |
| code | Enum | 응답 코드 (**[Error Code](../common/models.html#error-code)**) | O |
| message | String | 오류 메시지 |

<br><br>

[뒤로](../../../../../index.html)