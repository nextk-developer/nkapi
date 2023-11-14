---
layout: default
title: 모델 설정
description: 모델 설정을 변경 합니다.
---

# Get models
서버에 설정된 모델 항목을 가져옵니다.

## Request
```
POST /v2/va/get-models

{
    "NodeId": "e339d131d4a6bbc5",
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- |:----: |
| nodeId | String | 컴퓨팅 노드 ID | O |

## Response

### SUCCESS
```
{
    "Models": [
        {
            "BatchSize": 1,
            "CalibrationImagesPath": "null",
            "Debug": false,
            "DetectThresh": 0.5,
            "Enable": false,
            "GpuIds": [
                0
            ],
            "InferencePrecison": 0,
            "InputSize": [
                640,
                640
            ],
            "Labels": [
                {
                    "LabelId": 0,
                    "LabelName": "person"
                }
            ],
            "ModelWeightsPath": "yolov5_det/yolov5n_person.wts",
            "NetSubType": "n",
            "NetType": 2,
            "NmsThresh": 0.4000000059604645,
            "NumberOfFrameDivisions": -1,
            "Options": [],
            "PrintDetectedElpasedTime": false,
            "PrintDetectorFps": false,
            "TrtFileName": ""
        },
        {
            "BatchSize": 1,
            "CalibrationImagesPath": "null",
            "Debug": false,
            "DetectThresh": 0.800000011920929,
            "Enable": false,
            "GpuIds": [
                0
            ],
            "InferencePrecison": 0,
            "InputSize": [
                640,
                640
            ],
            "Labels": [
                {
                    "LabelId": 300,
                    "LabelName": "face"
                }
            ],
            "ModelWeightsPath": "retina/retina_mnet.wts",
            "NetSubType": "",
            "NetType": 4,
            "NmsThresh": 0.4000000059604645,
            "NumberOfFrameDivisions": -1,
            "Options": [
                {
                    "BatchSize": 1,
                    "CalibrationImagesPath": "configs/calibration_images.txt",
                    "Debug": false,
                    "DetectThresh": 0.6000000238418579,
                    "Enable": true,
                    "GpuIds": [
                        0
                    ],
                    "InferencePrecison": 0,
                    "InputSize": [
                        112,
                        112
                    ],
                    "Labels": [],
                    "ModelWeightsPath": "arc/arc_r50.wts",
                    "NetSubType": "",
                    "NetType": 101,
                    "NmsThresh": 0.4000000059604645,
                    "NumberOfFrameDivisions": 0,
                    "Options": [],
                    "PrintDetectedElpasedTime": false,
                    "PrintDetectorFps": false,
                    "TrtFileName": ""
                },
                {
                    "BatchSize": 1,
                    "CalibrationImagesPath": "configs/calibration_images.txt",
                    "Debug": false,
                    "DetectThresh": 0.800000011920929,
                    "Enable": true,
                    "GpuIds": [
                        0
                    ],
                    "InferencePrecison": 0,
                    "InputSize": [
                        0,
                        0
                    ],
                    "Labels": [],
                    "ModelWeightsPath": "mask/mask.onnx",
                    "NetSubType": "",
                    "NetType": 104,
                    "NmsThresh": 0.4000000059604645,
                    "NumberOfFrameDivisions": 0,
                    "Options": [],
                    "PrintDetectedElpasedTime": false,
                    "PrintDetectorFps": false,
                    "TrtFileName": ""
                }
            ],
            "PrintDetectedElpasedTime": false,
            "PrintDetectorFps": false,
            "TrtFileName": ""
        }
    ],
    "code": 0,
    "message": "SUCCESS"
}
``` 

| Name | Type | Description | Required |
| :---- | :---- |:---- |:----: |
| Models | JsonObject[] | [Model Config](#model-config) List | O |

### REQUEST_TIMEOUT Or Something
```
{
    "code": 502,
    "message": "REQUEST_TIMEOUT"
}
```

# Apply models
서버의 모델 설정을 변경합니다.

## Request
```
POST /v2/va/apply-models

{
    "Models": [
        {
            "BatchSize": 1,
            "CalibrationImagesPath": "null",
            "Debug": false,
            "DetectThresh": 0.5,
            "Enable": false,
            "GpuIds": [
                0
            ],
            "InferencePrecison": 0,
            "InputSize": [
                640,
                640
            ],
            "Labels": [
                {
                    "LabelId": 0,
                    "LabelName": "person"
                }
            ],
            "ModelWeightsPath": "yolov5_det/yolov5n_person.wts",
            "NetSubType": "n",
            "NetType": 2,
            "NmsThresh": 0.4000000059604645,
            "NumberOfFrameDivisions": -1,
            "Options": [],
            "PrintDetectedElpasedTime": false,
            "PrintDetectorFps": false,
            "TrtFileName": ""
        },
        {
            "BatchSize": 1,
            "CalibrationImagesPath": "null",
            "Debug": false,
            "DetectThresh": 0.800000011920929,
            "Enable": false,
            "GpuIds": [
                0
            ],
            "InferencePrecison": 0,
            "InputSize": [
                640,
                640
            ],
            "Labels": [
                {
                    "LabelId": 300,
                    "LabelName": "face"
                }
            ],
            "ModelWeightsPath": "retina/retina_mnet.wts",
            "NetSubType": "",
            "NetType": 4,
            "NmsThresh": 0.4000000059604645,
            "NumberOfFrameDivisions": -1,
            "Options": [
                {
                    "BatchSize": 1,
                    "CalibrationImagesPath": "configs/calibration_images.txt",
                    "Debug": false,
                    "DetectThresh": 0.6000000238418579,
                    "Enable": true,
                    "GpuIds": [
                        0
                    ],
                    "InferencePrecison": 0,
                    "InputSize": [
                        112,
                        112
                    ],
                    "Labels": [],
                    "ModelWeightsPath": "arc/arc_r50.wts",
                    "NetSubType": "",
                    "NetType": 101,
                    "NmsThresh": 0.4000000059604645,
                    "NumberOfFrameDivisions": 0,
                    "Options": [],
                    "PrintDetectedElpasedTime": false,
                    "PrintDetectorFps": false,
                    "TrtFileName": ""
                },
                {
                    "BatchSize": 1,
                    "CalibrationImagesPath": "configs/calibration_images.txt",
                    "Debug": false,
                    "DetectThresh": 0.800000011920929,
                    "Enable": true,
                    "GpuIds": [
                        0
                    ],
                    "InferencePrecison": 0,
                    "InputSize": [
                        0,
                        0
                    ],
                    "Labels": [],
                    "ModelWeightsPath": "mask/mask.onnx",
                    "NetSubType": "",
                    "NetType": 104,
                    "NmsThresh": 0.4000000059604645,
                    "NumberOfFrameDivisions": 0,
                    "Options": [],
                    "PrintDetectedElpasedTime": false,
                    "PrintDetectorFps": false,
                    "TrtFileName": ""
                }
            ],
            "PrintDetectedElpasedTime": false,
            "PrintDetectorFps": false,
            "TrtFileName": ""
        }
    ]
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- |:----: |
| Models | JsonObject[] | [Model Config](#model-config) List | O |

## Response

### SUCCESS
```
{
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


### Model Config

| Name | Type | Description | Required |
| :---- | :---- |:---- |:----: |
| Enable | bool | 사용 여부 | O |
| NetType | Enum | [모델종류](#detector-model-type) | O |
| NetSubType | Enum | [서브모델 종류](#detector-sub-type) | O |
| InferencePrecison | Enum | [정밀도](#datatype) | O |
| DetectThresh | Double | 검출 한계점 | O |
| NmsThresh | Double | NMS 한계점 | O |
| Labels | JsonObject[] | [라벨 설정](#label) | O |
| Options | JsonObject[] | [옵션 설정](#model-config) | O |
| ModelWeightsPath | String | 모델 경로 | O |
| CalibrationImagesPath | String | 켈리브레이션 이미지 경로 | O |
| TrtFileName | String | 엔진 파일 이름 | O |
| PrintDetectedElpasedTime | Boolean | 검출기 추론 시간 출력 여부 | O |
| PrintDetectorFps | Boolean | 검출기 총 FPS 출력 여부 | O |
| NumberOfFrameDivisions | Integer | 검출기 Fps (-1일시 자동 분배) | O |
| GpuIds | Integer[] | 사용할 GPU 설정 | O |
| InputSize | Integer[] | 입력 사이즈 (W, H) | O |
| BatchSize | Integer | 배치 사이즈 | O |
| Debug | Boolean | 디버깅 여부 (개발자 전용) | O |

### Label

| Name | Type | Description |
| :---- | :---- |:---- |
| LabelId | int | 라벨 ID |
| LabelName | String | 라벨 이름 |

### Detector Model Type

| Value | Enum | 
| :---- | :---- |
| 0 | YOLOV8 |
| 1 | YOLOV4 |
| 2 | YOLOV5 |
| 3 | YUNET |
| 4 | RETINA_MOBILE_NET |
| 5 | RETINA_COV |
| 6 | RETINA_R50 |
| 7 | RETINA_R100 |
| 8 | DEEPSPARSE |
| 9 | YOLOV5_ONNX |
| 100 | ARC_MOBILE_NET |
| 101 | ARC_R50 |
| 102 | ARC_R100 |
| 103 | ALPHA_POSE |
| 104 | MASK_CLASSIFICATION |
| 105 | LPR_NET |
| 106 | FAST_REID |
| 107 | YOLOV5_CLS |
| 108 | PPE_CLASSIFICATION |

### Detector Sub Type

| Value | Enum | 
| :---- | :---- |
| 0 | None |
| 1 | Nano |
| 2 | Small |
| 3 | Midium |
| 4 | Large |
| 5 | XLarge |

### DataType

| Value | Enum | 
| :---- | :---- |
| 0 | kFLOAT |
| 1 | kHALF |
| 2 | kINT8 |
| 3 | kINT32 |
| 4 | kBOOL |
| 5 | kUINT8 |
| 6 | kFP8 |


<br><br>

[뒤로](../../../../../index.html)