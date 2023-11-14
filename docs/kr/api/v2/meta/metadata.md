---
layout: default
title: 메타데이터 조회
description: 저장되어 있는 메타데이터를 조회합니다.<br>레코딩 설정이 선행 되어야 합니다.
---

# Metadata

## Request
```
POST /v2/va/metadata

{
    "nodeId": "813ee7995af2e8cd",
    "channelIds": ["cce679532768e7c5"],
    "eventTypes": [
      "AllDetect","Loitering","Intrusion","Falldown","Violence",
      "IllegalParking","AbnormalObjectCount","Longstay","LineEnter","LineCrossing","Direction","LeftTurn","RightTurn","UTurn",
      "Smoke","Flame","MatchingFace","NotWearingMask","NoHelmet","TrafficActuatedSignal"
    ],
    "progressFilter": [0],
    "classIdFilter": [
        0,100,102,103,104,105,106,107,108,109,110,111,112,300,200,201,4,5
    ],
    "startTime": "2023-06-09T17:42:34",
    "endTime": "2023-06-09T17:42:35",
    "includeThumbnail": true,
    "reIdObject": null
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- | :----: |
| nodeId | String | 컴퓨팅 노드 ID | O |
| channelIds | String[] | 채널 ID | O |
| eventTypes | String[] | 해당 이벤트 타입 조회 (**[EventType](../common/models.html#eventtype)**) | O |
| progressFilter | Integer[] | 진행 필터 (**[Progress](../common/models.html#progress)**) | O |
| classIdFilter | Integer[] | 해당 classId 조회 (**[ClassId](../common/models.html#classid)**) | O |
| startTime | String | 영상 재생 시작시간 (startTime ~ endTime 범위안의 영상 재생)| O |
| endTime | String | 영상 재생 끝나는시간 (startTime ~ endTime 범위안의 영상 재생)| O |
| includeThumbnail | Boolean | 썸네일 조회 여부 | O |
| reIdObject | JsonObject | 리아이디 조회 여부 | X |


## Response

### SUCCESS
```
{
    "objectMetas" : {
        "CameraName" : "NEXTK Channel",
        "CameraUID" : "9cea1c46176b8262",
        "EventList" : [],
        "FrameHeight" : 1920,
        "FrameNumber" : 9254,
        "FrameWidth" : 1080,
        ...
    }
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
| :---- | :---- |:---- | :----: |
| objectMetas | JsonObject[] | 메타 데이터 (**[ObjectMeta](../../../zmq/va_results.html)**) | O |
| code | Enum | 응답 코드 (**[Error Code](../common/models.html#error-code)**) | O |
| message | String | 오류 메시지 | X |


<br><br>

[뒤로](../../../../../index.html)