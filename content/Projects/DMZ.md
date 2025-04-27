---
comments: "false"
---
> 2022.03 ~ 2022.06
## 문제점
- 클라우드 서비스의 모니터링 지표만으로 고객의 서비스 안정성을 담보할 수 없음
- 고객과 동일한 서비스 레벨에서 모니터링 데이터를 수집해야 함
- 500대 이상의 KVM 장비에 더미 인스턴스가 설치되어 있었지만 제대로 관리되지 않고 있었음
- 모니터링 마스터 서버가 단일화되어 있어 장애에 취약한 상태였음
## 해결 방법
- Slash commands를 연동해 더미 인스턴스의 정합성을 확인하고 손쉽게 생성, 삭제할 수 있는 도구 개발
- ELK 스택을 활용해 더미 인스턴스의 이벤트 발생에 따른 데이터 수집 자동화
- AWS, KT Cloud를 활용해 서로 다른 외부 클라우드에서 모니터링할 수 있도록 DR 구성
## 구조

![[Pasted image 20250427121802.png]]
1. icingabeat로 더미 인스턴스의 모니터링 데이터 수집
2. 이벤트 형식에 따라 Logstash에서 파싱, ES로 전달
3. ES에 저장된 데이터를 Kibana 대시보드로 시각화, 레포트화
## 기술 스택
- Openstack SDK + FastAPI
- icinga
- ELK
- Docker
- Django, Slash commands
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

- 현재 2000개 이상의 KVM 장비에 대해 모니터링 데이터 수집 자동화
- icinga에서 추출한 엑셀 데이터를 기반으로 정리하는 방식 대비 95% 이상 공수 절약
- NHN Cloud 전반의 가용률과 Latency, 장애 이력 등을 확인할 수 있는 대시보드 단일화
- 객관적이고 정확한 실시간 지표로 경영진 운영 자료로 차용
## 기여도
- 사내 챗봇 Slash commands 개발 (100%)
- FastAPI 서버에 Openstack SDK 연동 (50%)
- Docker로 icinga 서버 구성 (30%)
- 외부 클라우드로 모니터링 서버 DR 구성 (100%)
- icingabeat + ELK 파이프라인 구축 (100%)
