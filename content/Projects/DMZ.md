---
comments: "false"
---
> 2022.03 ~ 2022.06
## 문제점
- 클라우드 서비스는 모니터링 지표만으로 실제 서비스 상태를 판단하기가 어려움
- 고객과 동일한 서비스 레벨에서 데이터를 수집하기 위해 모든 하이퍼바이저에 더미 인스턴스를 생성
- 500대가 넘는 더미 인스턴스가 제대로 관리되지 않는 상태였음
- 모니터링 마스터 서버가 단일화되어 있어 장애에 취약했음
- 모니터링 시스템에서 발생하는 모든 이벤트를 엑셀로 정리해 관리하고 있었음
## 해결 방법
- 더미 인스턴스 전수 조사, 신규 생성 및 삭제를 GUI로 손쉽게 할 수 있는 툴 개발
- AWS, KT Cloud를 활용해 모니터링 서버를 DR 구성
- ELK 스택을 도입해 더미 인스턴스에서 발생하는 모든 이벤트를 자동으로 수집하도록 개발
## 구조

![[Pasted image 20250427121802.png]]
## 기술 스택
- Openstack SDK + FastAPI
- icinga
- ELK
- Docker
## 도전
icingabeat는 이벤트가 발생할 때마다 logstash로 단일 데이터를 전송하게 됩니다.
즉 하나의 호스트에 장애가 발생해 통신이 단절되었다가 회복된 경우, 두 개의 독립된 이벤트가 전송됩니다.
따라서 호스트명과 서비스 정상 유무로 얼마만큼 통신이 단절되었는지 확인하는 작업이 필요했습니다.
Kibana로 대시보드를 구성하는 과정에서 `scripted filter`를 사용해 데이터를 후처리하고자 했지만, 하나의 도메인에서만 동작하기 때문에 두 개의 도메인을 사용해 단절 시간을 확인하는 것이 불가능했습니다.

이를 해소하기 위해 Logstash에서 데이터를 전처리하는 방식을 도입했고,
ES의 이전 데이터를 참조하는 코드를 추가해 데이터 필드에 단절 시간을 기록함으로써 원하는 방식으로 데이터를 저장할 수 있게 되었습니다.

```ruby
input {
  beats {
    port => 5044
    host => "..."
  }
}

filter {
  if [icinga][notification_type] == "RECOVERY" {
    mutate {
      add_field => { "event_end" => "${timestamp}" }
    }
    elasticsearch {
      hosts => ["..."]
      index => "elk-*"
      query => "icinga.notification_type:PROBLEM AND icinga.host.keyword:${[icinga][host]}"
      fields => {"@timestamp" => "started"}
    }
    date {...}
    ruby {...}
  }
}
```

## 결과
- 현재 2000대 이상의 인스턴스에 대해 이벤트 수집 중
- 인스턴스 수는 4배 이상 늘었지만 이벤트 데이터를 정리하는 데 95% 이상 공수 절약
- 이벤트 데이터를 기반으로 Kibana 대시보드 제작, 가용률과 장애 이력 등 데이터 제공
- 객관적이고 정확한 실시간 지표로 경영진 운영 자료로 차용
## 기여도
- FastAPI 서버 개발, Openstack SDK 연동 (50%)
	- 하이퍼바이저가 증설, 삭제될 때마다 GUI 기반으로 더미 인스턴스 생성 및 제거
- icinga 서버 구성 (60%)
	- AWS 4개 리전, KT Cloud에 icinga 서버를 구성해 운영
	- Docker-compose 기반으로 일관적인 서버 구축
- 외부 클라우드로 모니터링 서버 DR 구성 (100%)
	- 모니터링 대상을 동일하게 관리할 수 있도록 icinga API를 활용한 sync 기능 개발
- icingabeat + ELK 파이프라인 구축 (100%)
