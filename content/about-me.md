---
title: About Me
comments: "false"
---
## 👋 Introduce!
**안녕하세요, 판교에서 5년차 클라우드 시스템 엔지니어로 일하고 있는 한윤범입니다.**

모든 것에는 기본이 되는 가치가 있습니다. IT 분야의 모든 서비스는 결국 물리 서버를 기반으로 한 인프라 위에서 동작합니다. 제가 첫 번째 직업으로 시스템 엔지니어를 선택한 이유는 IT 분야를 가장 근본적인 곳에서부터 경험하고 싶었기 때문입니다.

NHN Cloud에서 시스템 엔지니어로 일하며 DevOps와 관련된 업무를 담당했습니다. 물리 서버 설치부터 컨테이너 기반의 모니터링 시스템까지 자체 IDC를 기반으로 한 퍼블릭 클라우드 서비스를 운영하며 배포, IaC 개발 및 모니터링 업무를 수행했습니다.

클라우드는 서비스 특성 상 글로벌 멀티 리전, 공공 리전 등 다양한 환경이 존재합니다. 이런 환경을 일관성 있게 유지하고 통합할 수 있도록 IaC를 개발하는 것에 많은 노력을 기울여왔습니다. 특히 CI/CD 파이프라인 개발, 테라폼 기반의 자동화 테스트를 도입해 팀 전체의 업무 시간을 주당 50시간 이상 줄였던 경험이 있습니다. 또한 통합 모니터링 시스템 구축을 통해 서비스 지표를 운영팀에 제공해 활용할 수 있도록 기여하기도 했습니다.

개인적으로는 본업 뿐만 아니라 게임 개발에도 시간을 투자하고 있습니다. 기획, 아트, 개발 분야의 5명으로 이루어진 팀으로 함께 인디게임을 개발하고 있습니다. Unity 엔진을 사용해 세 번의 글로벌 게임잼에 참여한 이력이 있으며, 게임 업계 전반을 경험하고 이해하는 데 힘쓰고 있습니다.

## 🧑🏻‍💻 Work
### NHN Cloud
> 2020.07. - 현재, System Engineer
> Public Cloud 서비스

- 20개 이상의 Openstack 기반 대규모 퍼블릭 클라우드 환경 구축, 운영
- CentOS, Ubuntu 등 Linux OS 기반의 서버 설치 및 운영, 자동화, 장애 대응
- Saltstack, Terraform 등 IaC를 활용한 IaaS 구성 및 테스트 자동화
- 배포 자동화를 위한 CI/CD 파이프라인 도입, 개발 및 운영
- 인프라 비용 절감을 위해 PM/VM 기반의 Openstack 컴포넌트를 컨테이너로 전환
- 클라우드 운영을 위한 RMQ 모니터링, 로그모니터링, 통합 모니터링 시스템 등 모니터링 툴 개발
- AWS, KT Cloud 등 타사 클라우드 인프라를 활용한 장애 감지 시스템 개발
- 신입사원 교육, 온보딩 가이드 문서화
### NHN
> 2020.01. - 2020.06, Intern
> Public Cloud 서비스

- Openstack Dev 환경 구축
- 13,000대 이상의 전사 인프라 물리 서버 및 부품 관리를 위한 자산관리 시스템 개발
- 업무 공유를 위한 메신저 기반의 일일 스크럼 Slash 커맨드 개발
### Define
> 2019.03. - 2019.08, Intern
> 제주시의 공공 편의시설 서비스를 제공하는 스타트업

- AI 학습을 위한 비정형 데이터 수집 및 분류
- NodeJS를 사용한 웹, 안드로이드 앱 기반의 풀스택 서비스 개발
## 🚀 Project

(프로젝트 제목을 클릭하면 상세 내용을 확인할 수 있습니다!)

### [[AC DC]]

> [!example] Auto Check for Deployment Code (AC/DC)
> 프로젝트 기간: 2023.09 ~ 2024.11
> 
> Openstack 기반 Public Cloud의 신규 기능을 안정적으로 배포하기 위한 프로젝트
> Github Actions를 활용해 코드를 검증하고 배포할 수 있는 CI/CD 파이프라인을 개발한 사례
> 
> 기술 스택: `github/actions`,  `python`,  `saltstack`
### [[Terraform Test]]

> [!example] 인프라 서비스 검증 자동화
> 프로젝트 기간: 2023.10 ~ 2024.03
> 
> 배포 후 NHN Cloud 서비스의 기본 기능을 검증하기 위한 프로젝트
> Terraform 및 Github Actions로 검증 과정을 자동화한 사례
> 
> 기술 스택: `terraform`,  `jenkins`,  `github/actions`, `kubernetes`
### [[DMZ]]

> [!example] 더미 모니터링 시스템
> 프로젝트 기간: 2022.03 ~ 2022.06
> 
> 고객과 동일한 환경에서 서비스 모니터링을 하기 위해 개발한 프로젝트
> ELK 스택을 이용해 모니터링 지표를 수집 및 가공, 레포트 생성을 자동화한 사례
> 
> 기술 스택: `icinga`,  `ELK`,  `docker`,  `django`, `openstack`

### [[WARD]]

> [!example] 통합 모니터링 플랫폼
> 프로젝트 기간: 2021.09 ~ 2022.03
> 
> NHN Cloud 관련 서비스 알림을 하나의 플랫폼으로 통합, 관리하기 위한 프로젝트
> 
> 기술 스택: `rabbitmq`,  `kubernetes`,  `fastapi`

## ⚡️ Skill
### OS
- 데이터센터 기반의 하드웨어 구성에 능숙하며 서비스 전면 장애 처리 경험을 가지고 있습니다.
- PXE 기반의 Linux 서버 설치 자동화, L2/L3 네트워크 트러블슈팅에 대한 경험이 있습니다.
- CentOS, Ubuntu 등 Linux OS를 주로 다루며 Bash 및 Python 스크립트를 개발하는 데 익숙합니다.
- 가상화 기법, 이중화 등 인프라를 안정적으로 운영하기 위한 적절한 지식을 가지고 있습니다.
- Vim 에디터 사용을 선호합니다.
### Openstack
- Openstack을 구성하는 컴포넌트의 특징을 이해하고 Dev 환경을 구축할 수 있습니다.
- Public Cloud의 IaaS 서비스에 익숙하며 복잡한 구성을 이해하고 구현할 수 있습니다.
- 컨테이너 기반으로 운영하기 위한 Helm 차트 개발, 무중단 Migration 작업을 수행한 경험이 있습니다.
### CI/CD
- Github Actions에 능숙하며 IaaS 배포를 위한 파이프라인을 처음으로 도입하고, 개발 및 운영했습니다.
- Git, Jenkins를 활용해 Debian 패키징을 자동화한 경험이 있습니다.
### IaC
- Saltstack 개발에 능숙하며 다양한 환경을 일관성 있게 관리할 수 있습니다.
- Terraform으로 Openstack, AWS 클라우드 리소스를 생성하는 데 익숙합니다.
- 효율적인 코드 관리를 위한 모듈화 및 자동화 구성을 할 수 있습니다.
### 모니터링
- ELK 기반의 로그 모니터링을 구현하고 트러블슈팅을 할 수 있습니다.
- icinga로 모니터링 툴을 구성하고 데이터 분석을 통한 레포트를 만들 수 있습니다.
- 리소스 사용량과 같은 로우데이터에 의미를 부여하고 시스템을 운영하는 데 필요한 가치있는 데이터로 가공할 수 있습니다.
- 통합 모니터링 시스템을 개발해 데이터를 취합하고 분류, 가공해 웹으로 제공한 경험이 있습니다.
### 웹개발
- Django를 사용한 RESTful API 개발에 익숙합니다.
- K8s 기반의 애플리케이션을 개발하고 운영할 수 있습니다.
- 조직의 업무 효율을 향상시키기 위해 슬래시 커맨드를 개발해 운영한 경험이 있습니다.
## 🔥 Other
### Game Development
> 2017.01. - 2017.12
> 2024.01. - 현재

Unity로 게임을 개발하는 취미를 가지고 있습니다. 다양한 시도를 통해 창의적인 게임을 만드는 것을 좋아합니다.
게임 개발에 필요한 시스템을 AWS, GCP에 구축하고 자동화 파이프라인을 만들어 활용하고 있습니다.
- [Bumpermon](https://github.com/han-yunb/bumpermon-pub) (개발, 기획)
- [Itch.io](https://bumbrogames.itch.io/)
	- Shoot! Hide! Run! (개발)
	- Visitor Guardian (개발)
	- I Thought This Was a Simple Delivery, But Now I’m the Strongest?! (개발)
### Presentation
- [오픈 인프라 서밋 후기](https://2023.openinfradays.kr/session/68) at OpenInfra Community Days Korea 2023
### KyungHee Univ.
> 경희대학교 컴퓨터공학과 (학사)
> 2013.03. - 2020.08

자료구조, OS, 오픈소스 소프트웨어 개발 등의 과목에 관심이 많은 대학생이었습니다.
교내 해커톤 대회에 참여해 입상하고 중학생을 대상으로 프로그래밍을 가르치는 등의 대외활동을 한 경험이 있습니다.
## 📞 Contact
Email. yunbum.han@gmail.com
Github. https://github.com/han-yunb
