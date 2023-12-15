---
layout: default
---

# 소개
NKAI API의 프로토콜은 **REST API(HTTP/JSON)**와 **ZMQ**로 구성됩니다.

### REST API
단방향 요청/응답 형식의 기능에 사용합니다.
- [컴퓨팅 노드](./docs/kr/api/v2/node/computing_node.html)
  - [노드 등록](./docs/kr/api/v2/node/computing_node.html#create-computing-node)
  - [노드 조회](./docs/kr/api/v2/node/computing_node.html#get-computing-node)
  - [노드 수정](./docs/kr/api/v2/node/computing_node.html#update-computing-node)
  - [노드 삭제](./docs/kr/api/v2/node/computing_node.html#remove-computing-node)
  - [채널 항목 조회](./docs/kr/api/v2/channel/channels.html#list-channel)
- [채널](./docs/kr/api/v2/channel/channels.html)
  - [채널 등록](./docs/kr/api/v2/channel/channels.html#register-channel)
  - [채널 수정](./docs/kr/api/v2/channel/channels.html#update-channel)
  - [채널 삭제](./docs/kr/api/v2/channel/channels.html#remove-channel)
  - [관심영역 항목 조회](./docs/kr/api/v2/va/roi.html#list-roi)
  - [관심영역 항목 조회](./docs/kr/api/v3/va/roi.html#list-roi) (**1.1.0 버전 부터3**)
  - [채널 링크 등록 / 해제](./docs/kr/api/v2/channel/link.html)
- [분석 설정](./docs/kr/api/v2/va/roi.html)
  - [이벤트 관심영역 등록](./docs/kr/api/v2/va/roi.html#create-roi)
  - [이벤트 관심영역 수정](./docs/kr/api/v2/va/roi.html#update-roi)
  - [이벤트 관심영역 삭제](./docs/kr/api/v2/va/roi.html#remove-roi)
  - [이벤트 관심영역 등록/수정](./docs/kr/api/v3/va/roi.html#add-or-update-roi) (**1.1.0 버전 부터3**)
  - [분석 제어](./docs/kr/api/v2/va/control.html)
  - [분석 일정 등록](./docs/kr/api/v2/va/schedule.html)
  - [얼굴](./docs/kr/api/v2/va/face.html)
    - [얼굴 등록](./docs/kr/api/v2/va/face.html#register-face-db)
    - [얼굴 삭제](./docs/kr/api/v2/va/face.html#remove-face-db)
    - [얼굴 항목 조회](./docs/kr/api/v2/va/face.html#list-face-db)
- [플레이백](./docs/kr/api/v2/playback/playback.html)
  - [플레이백 요청](./docs/kr/api/v2/playback/playback.html#playback)
  - [레코딩 일정 등록](./docs/kr/api/v2/playback/schedule.html)
- [메타 데이터](./docs/kr/api/v2/meta/metadata.html)
- [시스템](./docs/kr/api/v2/system/system.html)
  - [시스템 로그 조회](./docs/kr/api/v2/system/system.html#system-log)
  - [시스템 명령 전달](./docs/kr/api/v2/system/system.html#system)
- [모델 설정](./docs/kr/api/v2/models/models.html)
  - [모델 항목 조회](./docs/kr/api/v2/models/models.html#get-models)
  - [모델 항목 적용](./docs/kr/api/v2/models/models.html#apply-models)
- [공통 항목](./docs/kr/api/v2/common/models.html)

### ZMQ
메시지를 반복 전송하는 스트리밍 성격의 통신에 사용합니다.
- [분석 메타데이터 포멧](./docs/kr/zmq/va_results.html) (**1.1.0 버전 이전**)
- [분석 메타데이터 포멧](./docs/kr/zmq/va_results_v3.html) (**1.1.0 버전 부터**)
- [통계 데이터 포멧](./docs/kr/zmq/statistics.html) 
- [레코드 날짜 포멧](./docs/kr/zmq/record_date.html)
