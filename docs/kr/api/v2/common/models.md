---
layout: default
title: 공통 모델
description:  REST API 파라메터로 사용되는 JSON 오브젝트와 Enum들입니다.
---

# Channel

| Name | Type | Description |
| :---- | :---- |:---- |
| channelId | string | 채널 ID |
| inputUri | string | 입력 영상 주소 |
| channelName | string | 채널 이름 |
| inputType | Integer | 입력 영상 종류(**[InputType](models.md#inputtype)**) |
| status | Enum | 채널 상태 (**[ChannelStatus](#channelstatus)**)|

# ChannelStatus

| Enum | Description |
| :---- | :---- |
| CH_STATUS_NORMAL | 정상 |
| CH_STATUS_INPUT_DEVICE_CONNECTION_LOST | 입력장치 연결 끊김 |

# ObjectType

| Enum | Description |
| :---- | :---- |
| PERSON | 사람 |
| Vehicle | 차량 |
| Face | 얼굴 |
| Fire | 화재 |
| Head | 해드 |

# Roi Feature  

| Enum | Description |
| :---- | :---- |
| ALL | 내부/외부 객체 감지 |
| INSIDE | 내부 발생 감지 |
| OUTSIDE | 외부 발생 감지 |
| IGNORE | 비감지 |

# Roi Dot

| Name | Type | Description | 
| :---- | :---- |:---- |
| x | Integer | X 좌표 | 
| y | Integer | Y 좌표 |
| lineUntilNextDot | JsonObject[] | 검출 객체([RoiLine](#roi-line)) |

# Event Filter

| Name | Type | Description |
| :---- | :---- |:---- |
| minDetectSize | Integer | 최소 객체 크기 |
| maxDetectSize | Integer | 최대 객체 크기 |
| objectsTarget | enum | 검출 객체([ClassId](#classid)) |

# Roi Line

| Name | Type | Description |
| :---- | :---- |:---- |
| disable | boolean | 비활성화 | 
| direction | String | 방향 설정 | 
| target | JsonObject[] | 검출 객체([ObjectType](#object-type)) |

# EventType
이벤트 ROI 설정에 의해서 동작됩니다.
<br>
Direction, LeftTurn, RightTurn, UTurn 이벤트는 MultiLine으로 설정 후 Polygon으로 SubRoi를 등록 해야합니다.
설정된 SubRoi를 기반으로 시간 점유율, 공간 점유율, 구간 속도를 계산하게 됩니다.

| Enum | Description | Tools (Requirement)
| :---- | :---- |  :---- |
| Unknown | 이벤트 미발생 | None |
| AllDetect | 추적 객체를 이벤트로 발생합니다. | [Polygon / Rect]
| Loitering | 배회 | [Polygon / Rect]
| Intrusion | 침입 | [Polygon / Rect]
| Falldown | 쓰러짐 | [Polygon / Rect]
| Violence | 싸움 | [Polygon / Rect]
| IllegalParking | 불법 주정차 | [Polygon / Rect]
| AbnormalObjectCount | 영역 ROI 내 개체밀집 (정의된 개체수 이상의 객체 존재) | [Polygon / Rect]
| Longstay | 영역 ROI 내 장시간 체류(주정차) | [Polygon / Rect]
| LineEnter | Line ROI를 지나가는 객체감지 (Enter 방향) | [Line]
| LineCrossing | 양방향 라인 통과 | [Line]
| Direction | 방향성 이동 카운트 (좌, 우, 유턴 등) | [MultiLine, Polygon]
| LeftTurn | 차량 좌회전 | [MultiLine, Polygon]
| RightTurn | 차량 우회전 | [MultiLine, Polygon]
| UTurn | 차량 유턴 | [MultiLine, Polygon]
| Smoke | 화재 연기 | [Polygon / Rect]
| Flame | 화재 불꽃 | [Polygon / Rect]
| MatchingFace | 등록 얼굴 매칭 | [Polygon / Rect]
| NotWearingMask | 얼굴 마스크 미착용 | [Polygon / Rect]
| NoHelmet | 헬멧 미착용 | [Polygon / Rect]
| TrafficActuatedSignal | 차량 감응 신호 | [Polygon / Rect]
| NonDetectionArea | 비감지 영역 | [Polygon / Rect]
| TimeOccupancy | 시간 점유율 (ITS) | [Polygon / Rect]
| SpaceOccupancy | 공간 점유율 (ITS) | [Polygon / Rect]
| IntervalVelocity | 구간 속도 (ITS) | [Polygon / Rect]
| Headaway | 차두시간 (ITS) | [Polygon / Rect]
| QueueLength | 대기행렬길이 (ITS) | [Polygon / Rect]
| ElderlyPeople | 노약자 (지팡이, 휠체어) | [Polygon / Rect]
| PPE | 장구류 착용 이벤트 | [Polygon / Rect]
| TidyUpWorkbench | 작업대 정리 이벤트 | [Polygon / Rect]
| Leak | 누수 검출 이벤트 | [Polygon / Rect]

# ClassId

| Value | Name |
| :---- | :---- |
| 0 | Person |
| 2 | FallDown |
| 3 | Violence |
| 4 | Head |
| 5 | Helmet |
| 6 | Person_Cane |
| 7 | Person_BathChair |
| 8 | Person_Stroller |
| 100 | Vehicle |
| 101 | Micro (**Not Supported**)|
| 102 | Bike |
| 103 | MotorCycle |
| 104 | Sedan (**Not Supported**)|
| 105 | HatchBack (**Not Supported**)|
| 106 | Universal (**Not Supported**)|
| 107 | LiftBack (**Not Supported**)|
| 108 | Coupe (**Not Supported**)|
| 109 | Cabriolet (**Not Supported**)|
| 110 | Roadster (**Not Supported**)|
| 111 | Targa (**Not Supported**)|
| 112 | Limousine (**Not Supported**)|
| 113 | MuscleCar (**Not Supported**)|
| 114 | SportCart (**Not Supported**)|
| 115 | SuperCar (**Not Supported**)|
| 116 | Suv |
| 117 | Crossover (**Not Supported**)|
| 118 | Pickup |
| 119 | Van |
| 120 | Minivan (**Not Supported**)|
| 121 | Minibus (**Not Supported**)|
| 122 | CamperVan (**Not Supported**)|
| 123 | Special |
| 124 | Military (**Not Supported**)|
| 125 | Truck |
| 126 | FireTruck |
| 127 | ElectricCar (**Not Supported**)|
| 128 | PoliceCar (**Not Supported**)|
| 129 | Tractor |
| 130 | ForkLift |
| 131 | ReadyMixedConcrete |
| 132 | Excavators |
| 133 | TankLorry |
| 134 | Bus |
| 135 | Plate |
| 200 | Fire_Smoke |
| 201 | Fire_Flame |
| 300 | Face |
| 500 | Bag |
| 600 | Industry Crane |
| 601 | Industry Carrier |
| 602 | Industry Materials |
| 1000 | NonTrackingObjectFromThis |
| 1001 | Glove |
| 1002 | FaceShield |
| 1003 | SafetyShoes |
| 1004 | WeldingSleeve |
| 1005 | Cane |
| 1006 | BathChair |
| 1007 | Stroller |
| 1008 | Leak |

# LogType

| Value | Enum | Description |
| :----| :---- | :---- |
| 0 | None | 로그 없음 |
| 1 | Info | 일반 |
| 2 | Debug | 디버그 |
| 4 | Trace | 추적 |
| 8 | Critical | 심각 |
| 16 | Error | 오류 |
| 32 | Warning | 경고 |
| 64 | Event | 이벤트 |

# Functions

컴퓨팅 노드가 사용 가능한 기능들

| Enum | Description |
| :---- | :---- |
| FNC_CORE | 핵심 기능 |

# InputType
입력 비디오 타입

| Enum | Description |
| :---- | :---- |
| SRC_IPCAM_NORMAL | 일반 카메라 (Default) 영상 |
| SRC_IPCAM_THERMAL | 열화상 카메라 영상 |
| SRC_IPCAM_DEPTH | 깊이센서 카메라 영상 |
| SRC_ETC | 기타 영상 |

# SystemWarnings

| Enum | Description |
| :---- | :---- |
| SYS_RESOURCE_FULL | 시스템 리소스 한계 사용 중 |
| SYS_UNSTABLE_NETWORK | 네트워크 불안정 |
| SYS_NO_LICENSE | 라이센스 없음 |
| SYS_LICENSE_EXPIRED | 라이센스 만료 |

# Performance

| Name | Type | Description |
| :---- | :---- |:---- |
| cpuUsage | Double | CPU 사용률 |
| gpuUsage | Double | GPU 사용률 |
| memoryUsage | Double | Memory 사용률 |
| diskUsage | Double | Disk 사용률 |

# Version

| Name | Type | Description |
| :---- | :---- |:---- |
| software | String | NK 프로그램 버전 |
| detectorModel | Dynaimc Dictionary | model version |
| firmware | String | 펌웨어 버전 (OS) |
| gpuModel | String | GPU 모델 |
| gpuVersion | String | GPU 버전 |

# Calibration

| Name | Type | Description |
| :---- | :---- |:---- |
| focalLengthX | Double | 초첨거리 X | 
| focalLengthY | Double | 초첨거리 Y |
| principalX | Double | 원리좌표 X |
| principalY | Double | 원리좌표 Y |
| fov         | Double | 화각 |
| imageWorldX | Double | 이미지 월드좌표 X|
| imageWorldY | Double | 이미지 월드좌표 Y|
| imageWorldZ | Double | 이미지 월드좌표 Z|
| cameraPanDegree | Double | 카메라 Pan 각도 |
| cameraTiltDegree | Double | 카메라 Pan 각도 |
| cameraHorizontalAngle | Double | 카메라 수평각 |

### ROI Drawing Type

| Value | Name | Description
| :---- | :---- |:---- |
| 0 | None | 없음
| 1 | Polygon | 다각형
| 2 | Rect | 사각형
| 3 | Line | 라인 
| 4 | MultiLine | 멀티 라인 
| 5 | All | 전체 영역 

# Operations

비디오 분석 제어 명령들

| Value | Name | Description |
| :----| :---- | :---- |
| 0 | VA_START | 비디오 분석 시작/재개 |
| 1 | VA_STOP | 비디오 분석 중지 |
| 2 | VA_RESET | 비디오 분석 중 누적 집계된 값들을 모두 초기화 (즉, ROI 설정 직후 상태로 초기화) |

# Error code

| Value | Description |
| :---- | :---- |
| 0 | 성공 |
| 10 | api uri path 문제 |
| 11 | api 요청 데이터 포맷 문제 |
| 12 | 지원하지 않는 기능 |
| 20 | 라이선스 비활성화 |
| 21 | 라이선스 기간 만료 |
| 22 | 지원하지 않는 API 버전 |
| 23 | RPC 포트 문제 |
| 24 | HTTP 포트 문제 |
| 100 | 컴퓨팅 노드 생성 실패 |
| 101 | 컴퓨팅 노드 ID가 다름 |
| 200 | 채널 영상 수신 실패 |
| 201 | 채널 생성 실패 |
| 210 | 캘리브레이션 실패 |
| 220 | 스냅샷 생성 실패 |
| 300 | ROI 설정 실패 |
| 400 | 쿠다 오류 |
| 500 | 노드 연결 실패 |
| 501 | RTSP 포멧 오류 |
| 502 | 시간 초과 |
| 503 | 노드를 찾을 수 없음 |
| 504 | ROI를 찾을 수 없음 |
| 505 | 채널 ID를 찾을 수 없음 |
| 506 | 비디오를 찾을 수 없음 |
| 506 | 비디오 확장을 지원하지 않음 |
| 507 | 얼굴 감지기가 설정되지 않음 |
| 508 | 링크 포인트와 일치하지 않음 |

# LinkType

| Value | Name | Description
| :---- | :---- | :---- |
|0| None | 링크 미설정 |
|1| And | 링크 AND 설정 (양쪽에서 모두 감지) |
|2| Or | 링크 OR 설정 (둘중 하나만 감지) |

# Identifier

| Value | Name | Description
| :----| :---- | :---- |
| 0 | Normal | 일반 |
| 1 | White | 인가자 |
| 2 | Black | 비인가자 |

# Gender

| Value | Name | Description
| :----| :---- | :---- |
| 0 | Unknown | 식별 안됨 |
| 1 | Male | 남자 |
| 2 | Female | 여자 |

# Playback Protocol

| Value | Name |
| :----| :----|
| 0 | Rtsp |  
| 1 | Rtmp |
| 2 | WebRTC
| 2 | HLS | 

# Record Type

| Value | Enum | Description |
| :---- | :---- | :---- |
| 0 | None | 저장 안함 |
| 1 | Video | 영상 저장 |
| 2 | Event | 메타데이터 저장 |
| 3 | VideoNEvent | 영상, 메타데이터 저장 |

# Progress

| Value | Enum | Description |
| :---- | :---- | :---- |
| 0 | Begin | 진입 (이벤트 시작)|
| 1 | Continue | 진행 (이벤트 진행 중)|
| 2 | End | 종료 (이벤트 종료)|


# LinkedType

| Value | Enum | Description |
| :---- | :---- | :---- |
| 0 | None | 해제 |
| 1 | And | Main에서 Sub 까지 포함되서 검출 |
| 2 | Or | Main에서 Sub 둘 중 하나만 검출되도 검출 |


<br><br>

[뒤로](../../../../../index.html)