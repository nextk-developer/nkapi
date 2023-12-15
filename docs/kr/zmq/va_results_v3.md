---
layout: default
title: 비디오 분석 메타 포멧
description: 비디오 분석 결과는 분석 제어의 VA_START 이후 응답받은 IP, 와 Port의 조합으로 ZMQ의 PUB – SUB 방식으로 Subscribe 하여 수신할 수 있습니다.
---

# **Topic: CameraUID**

```
Sample

{
    "camera_name": "NEXTK Channel",
    "camera_uid": "b9126cb49314f61d",
    "event_list": [
        {
            "abnormal_s_core": 0.6080000000074506,
            "class_id": 0,
            "cls_items": ["shirt", "pants"],
            "event_detail": {
                "event_s_core": 0,
                "face": {
                    "age": 0,
                    "gender": 0,
                    "identify": 0,
                    "memo": "",
                    "name": ""
                },
                "face_uid": "",
                "key_points": {},
                "vehicle": {
                    "license_image_buffer": "",
                    "license_image_rect": {
                        "height": 0,
                        "width": 0,
                        "x": 0,
                        "y": 0
                    },
                    "license_plate": [1,2,3,4,5]
                }
            },
            "event_id": 1,
            "event_status": 1,
            "event_type": "AllDetect",
            "image_buffer": "",
            "image_rect": {
                "height": 0.2351851851851852,
                "width": 0.051041666666666666,
                "x": 0.7078125,
                "y": 0.4101851851851852
            },
            "inner_image_rect": {
                "height": 0,
                "width": 0,
                "x": 0,
                "y": 0
            },
            "is_detected": false,
            "is_event": true,
            "is_tracked": false,
            "object_color": {
                "b": 0,
                "g": 0,
                "r": 0
            },
            "object_id": 0,
            "object_prob": 0.8198726177215576,
            "roi_info": {
                "avg_stay_time": 0.32814285713746877,
                "roi": {
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
                },
                "roi_aggregated_data_items": {},
                "roi_object_counting": {
                    "entered_count": 7,
                    "exited_count": 7,
                    "object_count": 0
                }
            },
            "stay_time": 0
        }
    ],
    "frame_height": 1080,
    "frame_number": 4814,
    "frame_width": 1920,
    "time_stamp": "2023-11-14 07:31:26.5051722"
}
```

<br>

### ObjectMeta 
이벤트 결과 메타데이터 입니다. 

<br>

| Name | Type | Description |
| :---- | :---- |:---- |
| camera_uid | String | 채널 ID |
| camera_name | String | 채널 이름 |
| event_list | JsonObject | 이벤트 리스트 (**[EventInfo](va_results_v3.html#eventinfo)**) |
| frame_width | Integer | 영상 너비 |
| frame_height | Integer | 영상 높이 |
| frame_number | Integer | 영상 프레임 번호 |
| time_stamp | String | 영상 수신 시간 (YYYY-MM-DD HH:mm:ss.fff) |

<br>

### EventInfo
이벤트 리스트를 구성하는 객체입니다.
객체 추적 상태에는 3가지가 있고 검출, 추적, 이벤트가 있습니다.

**검출** : IsDetected: true, IsEvent: false, IsTracked: false

**추적**: IsDetected: false, IsEvent: false, IsTracked: true

**이벤트**: IsDetected: false, IsEvent: true, IsTracked: false

| Name | Type | Description |
| :---- | :---- |:---- |
| abnormal_score | Double | 계산된 이상수치 (이벤트 타입별로 정체지수, 체류시간, 자세이상수치) |
| is_detected | bool | 검출 검출 상태 |
| is_tracked | bool | 객체 추적 상태 |
| is_event | bool | 이벤트 발생 상태 |
| class_id | Integer | 채널 ID (**[ClassId](../api/v3/common/models.html/#classid)**) |
| object_prob | Double | 검출된 객체의 정확도 |
| object_id | Integer | 객체 ID |
| event_id | Integer | 자동 할당된 이벤트 ID (동일한 타입의 이벤트가 여럿 존재할 경우 구분 목적) |
| event_status | Enum | 이벤트 진행 상태 (**[Progress](../api/v3/common/models.html/#progress)**) |
| event_type | String | 이벤트 타입 (**[EventType](../api/v3/common/models.html/#eventtype)**) |
| roi_info | JsonObject[] | 관심 영역 정보 (**[RoiInfo](#roi-info)**) |
| stay_time | Double | 체류 시간 |
| image_buffer | String(Base64 Encoding) | 이벤트 진행 상태가 Begin일때만 전달됩니다. (이벤트 객체 섬네일) |
| image_rect | JsonObject[] | 검출된 객체 좌표 (**[ImageRect](../api/v3/common/models.html#imagerect)**) |
| inner_image_rect | JsonObject[] | [deprecated] ~~검출된 객체 내 객체의 좌표~~ (**[ImageRect](../api/v3/common/models.html#imagerect)**) |
| object_color | JsonObject[] | 바운딩 박스 색상 (**[ObjectColor](#objectcolor)**) |
| event_detail | JsonObject | 이벤트 디테일 (**[EventDetail](#eventdetail)**) |
| cls_items | String[] | 분류 항목 아이템 |




### Roi Info

| Name | Type | Description |
| :---- | :---- |:---- |
| roi | JsonObject | 관심 영역 정보 (**[ROI](../api/v3/common/models.html#roi)**)|
| avg_stay_time | Double | 평균 체류 시간 |
| roi_object_counting | JsonObject | 객체의 진입/진출/내부 수 (**[RoiObjectCouting](#roi-object-counting)**) |
| roi_aggregated_data_items | JsonObject | 영역안에 진입한 총 객체 수 (**[RoiAggregatedData](#roi-aggregated-data)**) |


### Roi Object Counting

| Name | Type | Description |
| :---- | :---- |:---- |
| object_count | Integer | 현재 영역안의 객체 수 |
| entered_count | Integer | 영역안에 진입한 총 객체 수 |
| exited_count | Integer | 영역밖으로 진출한 총 객체 수 |

### Roi Aggregated Data

| Name | Type | Description |
| :---- | :---- |:---- |
| max | Double | 가장 높은 수치 |
| min | Double | 가장 낮은 수치 |
| avg | Double | 평귱 수치 |
| cur | Double | 현재 수치 |



### EventDetail

| Name | Type | Description |
| :---- | :---- |:---- |
| face_id | String | 객체 ID |
| event_score | Double | 이벤트 정확도 |
| face | JasonObject | 얼굴 정보 (**[Face](#face)**) |
| key_points | JasonObject[] | 키 포인트 (**[KeyPoints](#keypoints)**) |
| vehicle | JasonObject | 차량 (**[Vehicle](#vehicle)**) |

### Face

| Name | Type | Description |
| :---- | :---- |:---- |
| name | String | 객체 이름 |
| age | Integer | 객체 나이 |
| gender | Integer | 객체 성별 |
| identify | Enum | 객체 구분 (**[Identify](#identify)**) |
| memo | String | 메모 |

### KeyPoints

| Name | Type | Description |
| :---- | :---- |:---- |
| x | Double | 키 포인트 X좌표 |
| y | Double | 키 포인트 Y좌표 |
| score | Double | 정확도 |

### Identify

| Name |  Description |
| :---- | :---- |
| Normal | 일반 |
| White | 인가자 |
| Black | 비인가자 |

<br>

### ObjectColor
추적하는 객체를 구분할 때 사용되며 id별로 다른 색상을 가집니다.

| Name | Type | Description |
| :---- | :---- |:---- |
| r | Integer | 빨강 |
| g | Integer | 초록|
| b | Integer| 파랑 |

### Vehicle
번호판 인식은 현재 개발 중입니다.

| Name | Type | Description |
| :---- | :---- | :---- |
| license_plate | Integer[] | 번호판 배열 (**미구현**)|
| license_image_rect | JsonObject[] | 번호판 좌표 및 크기 (**[ImageRect](../api/v3/common/models.html#imagerect)**) |
| license_image_buffer | String | 번호판 이미지 정보 (Base64 Encoding) |

<br><br>

[뒤로](../../../index.html)