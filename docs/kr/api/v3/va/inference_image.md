---
layout: default
title: 이미지 단일 추론
description: 단일 이미지를 서버에 설정된 모델로 분석하여 메타데이터를 수신 받을 수 있습니다.
---


## Request
```
POST /v3/va/inference-image

{
    "node_id": "53ae8e84be6e03bb",
    "image_buffer": "/9j/4AAQSkZJRgABAQEAYABgAAD/2...."
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- |:----: |
| node_id | String | 컴퓨팅 노드 ID | O |
| image_buffer | String | 이미지 정보 (Base64 Encoding) | O |


## Response
### SUCCESS
```
{
    "code": 0,
    "message": "SUCCESS",
    "meta": {
        "camera_name": "NEXTK Channel",
        "camera_uid": "b9126cb49314f61d",
        "event_list": [
            {
                "abnormal_score": 0.6080000000074506,
                "class_id": 0,
                "directional_type": 7,
                "cls_items": [
                    "shirt",
                    "pants"
                ],
                "event_detail": {
                    "event_score": 0,
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
                        "license_plate": [
                            1,
                            2,
                            3,
                            4,
                            5
                        ]
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
                    "roi_aggregated_data_items": {
                        "IntervalVelocity": {
                            "max": 0,
                            "min": 0,
                            "avg": 0,
                            "cur": 0
                        }
                    },
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
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- |:----: |
| code | Enum | 응답 코드 (**[Error Code](../common/models.html#error-code)**) | O |
| object_meta | JsonObject | 이벤트 결과 메타데이터(**[ObjectMeta](../../../zmq/va_results_v3.html)**) | O |
| message | String | 오류 메시지 | X |


### REQUEST_TIMEOUT or Somethings
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
| code | Enum | 응답 코드 (**[Error Code](../common/models.html#error-code)**) | O |
| message | String | 오류 메시지 | X |

<br><br>

[뒤로](../../../../../index.html)