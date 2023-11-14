---
layout: default
title: 저장된 날짜 메타 포멧
description: 노드를 생성후 응답받은 TargetPort와 RpcPort의 조합으로 ZMQ의 PUB – SUB 방식으로 Subscribe하여 수신할 수 있습니다.<br>서버의 설정된 레코딩 날짜에 따라 수신 할 수 있습니다.

---

# **Topic: record-date**

```
Sample

{
    "mediaRecord": {
        "b9126cb49314f61d": [
            "2023-11-14"
        ]
    },
    "metaRecord": {
        "27f2145494a4f20d": [
            "2023-11-14"
        ],
        "b9126cb49314f61d": [
            "2023-11-14"
        ]
    }
}
```

### Record Date

| Name | Type | Description |
| :---- | :---- |:---- |
| mediaRecord | JsonObject | 채널 별 영상 저장된 날짜 |
| metaRecord | JsonObject | 채널 별 메타 저장된 날짜 |

<br><br>

[뒤로](../../../index.html)