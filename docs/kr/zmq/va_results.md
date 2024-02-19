---
layout: default
title: 비디오 분석 메타 포멧
description: 비디오 분석 결과는 분석 제어의 VA_START 이후 응답받은 IP, 와 Port의 조합으로 ZMQ의 PUB – SUB 방식으로 Subscribe 하여 수신할 수 있습니다.
---

# **Topic: CameraUID**

```
Sample

{
    "CameraName": "NEXTK Channel",
    "CameraUID": "b9126cb49314f61d",
    "EventList": [
        {
            "AbnormalScore": 0.6080000000074506,
            "ClassID": 0,
            "ClsItems": ["shirt", "[pants]"],
            "EventDetail": {
                "EventScore": 0,
                "Face": {
                    "Age": 0,
                    "Gender": 0,
                    "Identify": 0,
                    "Memo": "",
                    "Name": ""
                },
                "FaceUID": "",
                "KeyPoints": {},
                "Vehicle": {
                    "LicenseImageBuffer": "",
                    "LicenseImageRect": {
                        "Height": 0,
                        "Width": 0,
                        "X": 0,
                        "Y": 0
                    },
                    "LicensePlate": [1,2,3,4,5]
                }
            },
            "EventID": 1,
            "EventStatus": 1,
            "EventType": "AllDetect",
            "ImageBuffer": "",
            "ImageRect": {
                "Height": 0.2351851851851852,
                "Width": 0.051041666666666666,
                "X": 0.7078125,
                "Y": 0.4101851851851852
            },
            "InnerImageRect": {
                "Height": 0,
                "Width": 0,
                "X": 0,
                "Y": 0
            },
            "IsDetected": false,
            "IsEvent": true,
            "IsTracked": false,
            "ObjectColor": {
                "B": 0,
                "G": 0,
                "R": 0
            },
            "ObjectID": 0,
            "ObjectProb": 0.8198726177215576,
            "RoiInfo": {
                "AvgStayTime": 0.3040000000037253,
                "RoiAggregatedDataItems": {},
                "RoiName": "",
                "RoiNumber": 0,
                "RoiObjectCounting": {
                    "EnteredCount": 2,
                    "ExitedCount": 1,
                    "ObjectCount": 1
                },
                "RoiUid": "f1d2b0cd38d7bd3d"
            },
            "StayTime": 0
        },
        {
            "AbnormalScore": 0,
            "ClassID": 0,
            "ClsItems": [],
            "EventDetail": {
                "EventScore": 0,
                "Face": {
                    "Age": 0,
                    "Gender": 0,
                    "Identify": 0,
                    "Memo": "",
                    "Name": ""
                },
                "FaceUID": "",
                "KeyPoints": {},
                "Vehicle": {
                    "LicenseImageBuffer": "",
                    "LicenseImageRect": {
                        "Height": 0,
                        "Width": 0,
                        "X": 0,
                        "Y": 0
                    },
                    "LicensePlate": []
                }
            },
            "EventID": -1,
            "EventStatus": 1,
            "EventType": "Unknown",
            "ImageBuffer": "",
            "ImageRect": {
                "Height": 0.11481481481481481,
                "Width": 0.059895833333333336,
                "X": 0.8869791666666667,
                "Y": 0.8796296296296297
            },
            "InnerImageRect": {
                "Height": 0,
                "Width": 0,
                "X": 0,
                "Y": 0
            },
            "IsDetected": false,
            "IsEvent": false,
            "IsTracked": true,
            "ObjectColor": {
                "B": 0,
                "G": 255,
                "R": 128
            },
            "ObjectID": 3,
            "ObjectProb": 0.6530802249908447,
            "RoiInfo": {
                "AvgStayTime": 0,
                "RoiAggregatedDataItems": {},
                "RoiName": "",
                "RoiNumber": -1,
                "RoiObjectCounting": {
                    "EnteredCount": 0,
                    "ExitedCount": 0,
                    "ObjectCount": 0
                },
                "RoiUid": ""
            },
            "StayTime": 0
        }
    ],
    "FrameHeight": 1080,
    "FrameNumber": 4814,
    "FrameWidth": 1920,
    "NodeUID": "a1418d0df36de6c6",
    "TimeStamp": "2023-11-14 07:31:26.5051722"
}
```

<br>

### ObjectMeta 
이벤트 결과 메타데이터 입니다.

<br>

| Name | Type | Description |
| :---- | :---- |:---- |
| NodeUID | String | 분석 서버 ID |
| CameraUID | String | 채널 ID |
| CameraName | String | 채널 이름 |
| EventList | JsonObject | 이벤트 리스트 (**[EventInfo](va_results.html#eventinfo)**) |
| FrameWidth | Integer | 영상 너비 |
| FrameHeight | Integer | 영상 높이 |
| FrameNumber | Integer | 영상 프레임 번호 |
| TimeStamp | String | 영상 수신 시간 (YYYY-MM-DD HH:mm:ss.fff) |

<br>

### EventInfo
이벤트 리스트를 구성하는 객체입니다.
객체 추적 상태에는 3가지가 있고 검출, 추적, 이벤트가 있습니다.

**검출** : IsDetected: true, IsEvent: false, IsTracked: false

**추적**: IsDetected: false, IsEvent: false, IsTracked: true

**이벤트**: IsDetected: false, IsEvent: true, IsTracked: false

| Name | Type | Description |
| :---- | :---- |:---- |
| AbnormalScore | Double | 계산된 이상수치 (이벤트 타입별로 정체지수, 체류시간, 자세이상수치) |
| IsDetected | bool | 검출 검출 상태 |
| IsTracked | bool | 객체 추적 상태 |
| IsEvent | bool | 이벤트 발생 상태 |
| ClassID | Integer | 채널 ID (**[ClassId](../api/v2/common/models.html/#classid)**) |
| ObjectProb | Double | 검출된 객체의 정확도 |
| ObjectID | Integer | 객체 ID |
| EventID | Integer | 자동 할당된 이벤트 ID (동일한 타입의 이벤트가 여럿 존재할 경우 구분 목적) |
| EventStatus | Enum | 이벤트 진행 상태 (**[Progress](../api/v2/common/models.html/#progress)**) |
| EventType | String | 이벤트 타입 (**[EventType](../api/v2/common/models.html/#eventtype)**) |
| RoiInfo | JsonObject[] | 관심 영역 정보 (**[RoiInfo](#roi-info)**) |
| StayTime | Double | 체류 시간 |
| ImageBuffer | String(Base64 Encoding) | 이벤트 진행 상태가 Begin일때만 전달됩니다. (이벤트 객체 섬네일) |
| ImageRect | JsonObject[] | 검출된 객체 좌표 (**[ImageRect](#imagerect)**) |
| InnerImageRect | JsonObject[] | [deprecated] ~~검출된 객체 내 객체의 좌표~~ (**[ImageRect](#imagerect)**) |
| ObjectColor | JsonObject[] | 바운딩 박스 색상 (**[ObjectColor](#objectcolor)**) |
| EventDetail | JsonObject | 이벤트 디테일 (**[EventDetail](#eventdetail)**) |
| ClsItems | String[] | 분류 항목 아이템 |

### Roi Info

| Name | Type | Description |
| :---- | :---- |:---- |
| RoiUid | String | 관심 영역 ID |
| RoiName | String | 관심 영역 별칭 |
| RoiNumber | Integer | 관심 영역 번호 (혹은 차로로 구분) |
| AvgStayTime | Double | 평균 체류 시간 |
| RoiObjectCounting | JsonObject | 객체의 진입/진출/내부 수 (**[RoiObjectCouting](#roi-object-counting)**) |
| RoiAggregatedDataItems | JsonObject | 영역안에 진입한 총 객체 수 (**[RoiAggregatedData](#roi-aggregated-data)**) |

### Roi Object Counting

| Name | Type | Description |
| :---- | :---- |:---- |
| ObjectCount | Integer | 현재 영역안의 객체 수 |
| EnteredCount | Integer | 영역안에 진입한 총 객체 수 |
| ExitedCount | Integer | 영역밖으로 진출한 총 객체 수 |

### Roi Aggregated Data

| Name | Type | Description |
| :---- | :---- |:---- |
| Max | Double | 가장 높은 수치 |
| Min | Double | 가장 낮은 수치 |
| Avg | Double | 평귱 수치 |
| Cur | Double | 현재 수치 |

### EventDetail

| Name | Type | Description |
| :---- | :---- |:---- |
| FaceUID | String | 객체 ID |
| EventScore | Double | 이벤트 정확도 |
| Face | JasonObject | 얼굴 정보 (**[Face](#face)**) |
| KeyPoints | JasonObject[] | 키 포인트 (**[KeyPoints](#keypoints)**) |
| Vehicle | JasonObject | 차량 (**[Vehicle](#vehicle)**) |

### ImageRect
모든 수치는 실제 객체 크기 / 프레임 크기 입니다.

| Name | Type | Description |
| :---- | :---- |:---- |
| Height | Double | 이미지 높이 |
| Width | Double | 이미지 너비 |
| X | Double | 이미지 X 좌표 |
| Y | Double | 이미지 Y 좌표 |

### Face

| Name | Type | Description |
| :---- | :---- |:---- |
| Name | String | 객체 이름 |
| Age | Integer | 객체 나이 |
| Gender | Integer | 객체 성별 |
| Identify | Integer | 객체 구분 (**[Identify](#identify)**) |
| Memo | String | 메모 |

### KeyPoints

| Name | Type | Description |
| :---- | :---- |:---- |
| X | Double | 키 포인트 X좌표 |
| Y | Double | 키 포인트 Y좌표 |
| Score | Double | 정확도 |

### Identify

| Name |  Description |
| :---- | :---- |
| Score | 정확도 |
| Normal | 일반 |
| White | 인가자 |
| Black | 비인가자 |

<br>

### ObjectColor
추적하는 객체를 구분할 때 사용되며 id별로 다른 색상을 가집니다.

| Name | Type | Description |
| :---- | :---- |:---- |
| R | Integer | 빨강 |
| G | Integer | 초록|
| B | Integer| 파랑 |

### Vehicle
번호판 인식은 현재 개발 중입니다.

| Name | Type | Description |
| :---- | :---- | :---- |
| LicensePlate | String | 번호판 문자열 (UTF8) |
| LicenseImageRect | JsonObject[] | 번호판 좌표 및 크기 (**[ImageRect](#imagerect)**) |
| LicenseImageBuffer | String | 번호판 이미지 정보 (Base64 Encoding) |

<br><br>

[뒤로](../../../index.html)