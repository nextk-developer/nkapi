---
layout: default
title: 영상 레코딩 설정
description: 채널 단위 영상 레코딩 설정을 할 수 있습니다. 
---

## Request
```
POST /v2/va/recording-schedule

{
    "nodeId": "3f16f31ecc13647d",
    "channelId": "5939a61ad39c0c37",
    "schedule": [
          [
              {"time":0,"type":0},{"time":1,"type":0},{"time":2,"type":0},{"time":3,"type":0},{"time":4,"type":0},{"time":5,"type":0},
              {"time":6,"type":0},{"time":7,"type":0},{"time":8,"type":0},{"time":9,"type":0},{"time":10,"type":0},{"time":11,"type":0},
              {"time":12,"type":0},{"time":13,"type":0},{"time":14,"type":0},{"time":15,"type":0},{"time":16,"type":0},{"time":17,"type":0},
              {"time":18,"type":0},{"time":19,"type":0},{"time":20,"type":0},{"time":21,"type":0},{"time":22,"type":0},{"time":23,"type":0}
          ],
          [   
              {"time":0,"type":0},{"time":1,"type":0},{"time":2,"type":0},{"time":3,"type":0},{"time":4,"type":0},{"time":5,"type":0},
              {"time":6,"type":0},{"time":7,"type":0},{"time":8,"type":0},{"time":9,"type":0},{"time":10,"type":0},{"time":11,"type":0},
              {"time":12,"type":0},{"time":13,"type":0},{"time":14,"type":0},{"time":15,"type":0},{"time":16,"type":0},{"time":17,"type":0},
              {"time":18,"type":0},{"time":19,"type":0},{"time":20,"type":0},{"time":21,"type":0},{"time":22,"type":0},{"time":23,"type":0}
          ],
          [
              {"time":0,"type":0},{"time":1,"type":0},{"time":2,"type":0},{"time":3,"type":0},{"time":4,"type":0},{"time":5,"type":0},
              {"time":6,"type":0},{"time":7,"type":0},{"time":8,"type":0},{"time":9,"type":0},{"time":10,"type":0},{"time":11,"type":0},
              {"time":12,"type":0},{"time":13,"type":0},{"time":14,"type":0},{"time":15,"type":0},{"time":16,"type":0},{"time":17,"type":0},
              {"time":18,"type":0},{"time":19,"type":0},{"time":20,"type":0},{"time":21,"type":0},{"time":22,"type":0},{"time":23,"type":0}
          ],
          [
              {"time":0,"type":0},{"time":1,"type":0},{"time":2,"type":0},{"time":3,"type":0},{"time":4,"type":0},{"time":5,"type":0},
              {"time":6,"type":0},{"time":7,"type":0},{"time":8,"type":0},{"time":9,"type":0},{"time":10,"type":0},{"time":11,"type":0},
              {"time":12,"type":0},{"time":13,"type":0},{"time":14,"type":0},{"time":15,"type":0},{"time":16,"type":0},{"time":17,"type":0},
              {"time":18,"type":0},{"time":19,"type":0},{"time":20,"type":0},{"time":21,"type":0},{"time":22,"type":0},{"time":23,"type":0}
          ],
          [
              {"time":0,"type":0},{"time":1,"type":0},{"time":2,"type":0},{"time":3,"type":0},{"time":4,"type":0},{"time":5,"type":0},
              {"time":6,"type":0},{"time":7,"type":0},{"time":8,"type":0},{"time":9,"type":0},{"time":10,"type":0},{"time":11,"type":0},
              {"time":12,"type":0},{"time":13,"type":0},{"time":14,"type":0},{"time":15,"type":0},{"time":16,"type":0},{"time":17,"type":0},
              {"time":18,"type":0},{"time":19,"type":0},{"time":20,"type":0},{"time":21,"type":0},{"time":22,"type":0},{"time":23,"type":0}
          ],
          [
              {"time":0,"type":0},{"time":1,"type":0},{"time":2,"type":0},{"time":3,"type":0},{"time":4,"type":0},{"time":5,"type":0},
              {"time":6,"type":0},{"time":7,"type":0},{"time":8,"type":0},{"time":9,"type":0},{"time":10,"type":0},{"time":11,"type":0},
              {"time":12,"type":0},{"time":13,"type":0},{"time":14,"type":0},{"time":15,"type":0},{"time":16,"type":0},{"time":17,"type":0},
              {"time":18,"type":0},{"time":19,"type":0},{"time":20,"type":0},{"time":21,"type":0},{"time":22,"type":0},{"time":23,"type":0}
          ],
          [
              {"time":0,"type":0},{"time":1,"type":0},{"time":2,"type":0},{"time":3,"type":0},{"time":4,"type":0},{"time":5,"type":0},
              {"time":6,"type":0},{"time":7,"type":0},{"time":8,"type":0},{"time":9,"type":0},{"time":10,"type":0},{"time":11,"type":0},
              {"time":12,"type":0},{"time":13,"type":0},{"time":14,"type":0},{"time":15,"type":0},{"time":16,"type":0},{"time":17,"type":0},
              {"time":18,"type":0},{"time":19,"type":0},{"time":20,"type":0},{"time":21,"type":0},{"time":22,"type":0},{"time":23,"type":0}
          ]
    ],
    "except": [
      "01.01","03.01","05.05","06.06","08.15","10.03","10.09","12.25"
    ]
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- |:----: |
| nodeId | String | 컴퓨팅 노드 ID | O |
| channelId | String | 채널 ID | O |
| schedule | JsonObject[][] | [(일 ~ 토)][(0 ~ 23)] = (**[Schedule](#schedule)**) | O |
| except | String[] | 레코드 제외 날짜 | X |

## Response
```
// SUCCESS
{
    "code": 0,
    "message" : ""
}
```

| Name | Type | Description | Required |
| :---- | :---- |:---- | :----: |
| code | Enum | 응답 코드 (**[Error Code](../common/models.html#error-code)**) | O |
| message | String | 오류 메시지 | X |

### Schedule

| Name | Type | Description |
| :---- | :---- |:---- |
| time | Integer | 레코드 시간 |
| type | Integer | 레코드 타입 (**[RecordType](../common/models.html#record-type)**) |


<br><br>

[뒤로](../../../../../index.html)