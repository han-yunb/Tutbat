---
title: About Me
comments: "false"
date: 2025-10-13
---
## 👋 Introduce!
**안녕하세요, 시스템 엔지니어로 일하고 있는 한윤범입니다.**

모든 것에는 기본이 되는 가치가 있습니다. IT 분야의 모든 서비스는 결국 물리 서버를 기반으로 한 인프라 위에서 동작합니다. 제가 첫 번째 직업으로 시스템 엔지니어를 선택한 이유는 IT 분야를 가장 근본적인 곳에서부터 경험하고 싶었기 때문입니다.

NHN Cloud에서 클라우드 시스템 엔지니어로 일하며 IaaS 관련 업무를 담당했습니다. 물리 서버 설치부터 컨테이너 기반의 모니터링 시스템까지 자체 IDC를 기반으로 한 퍼블릭 클라우드 서비스를 운영하며 배포, IaC 개발 및 모니터링 업무를 수행했습니다.

토스에 합류한 이후에는 Infra Engineering Tribe에 소속되어 사내 인프라를 관리하고 있습니다.

개인적으로는 본업 뿐만 아니라 게임 개발에도 시간을 투자하고 있습니다. 기획, 아트, 개발 분야의 5명으로 이루어진 팀으로 함께 인디게임을 개발하고 있습니다. Unity 엔진을 사용해 세 번의 글로벌 게임잼에 참여한 이력이 있으며, 게임 업계 전반을 경험하고 이해하는 데 힘쓰고 있습니다.

## 🧑🏻‍💻 Work
### Toss (Viva Republica)
> System Engineer
> 2025.10. - 현재
- Openstack 기반의 사내 인프라 업무 담당
### NHN Cloud
> System Engineer
> 2020.07. - 2025.10.
- 퍼블릭/공공/Private 클라우드 시스템 구축, 운영
	- Openstack 기반 멀티 리전/가용 영역 구성 및 서비스 제공 업무 수행
	- RHEL/CentOS 계열의 Linux 물리/가상 서버 운영, 커널 파라미터 튜닝, 시스템 설정 최적화, 운영 업무 자동화에 필요한 Shell script 개발
	- 하드웨어 및 가상화 레벨의 시스템 장애 트러블슈팅 및 해결 경험 (VMWare, Ovirt, Openstack)
	- CSAP 인증 등급 공공기관 환경, Private Cloud 인프라 구성 및 운영
- 고가용성 인프라 구성 및 네트워크 운영
	- HAProxy, Keepalived 기반의 Public, Internal API 서비스 구성 및 운영 업무 경험
	- 멀티 리전 간 이미지 파일 및 메타데이터 복제를 위한 인프라 구성 및 유지보수, SSL 인증서 적용, 공인 통신을 위한 라우팅 정책 적용
	- 대규모 트래픽 대응 및 부하 분산을 위한 서버 Scale Out 및 요청 분석, 근본 원인 해소 경험
- IaaS 컨테이너화 및 시스템 마이그레이션
	- Openstack 컴포넌트의 Kubernetes 전환을 위한 helm chart 개발 및 배포 업무 수행
	- 컨테이너 이미지 빌드를 위한 Jenkins 파이프라인 구축
	- GitOps 패턴을 기반으로 한 ArgoCD 도입 검토 및 PoC 수행
- Saltstack 기반의 IaC 개발
	- YAML 및 Jinja 템플릿을 활용한 Openstack 컴포넌트 구성 자동화
	- 배포 자동화를 통한 프로비저닝 시간 단축, 운영자 실수 감소를 통한 안정성 향상
	- 멀티 리전, Staging/Production 환경 대응을 위한 환경별 설정 관리 체계 구축
	- Git 기반 형상 관리, GitFlow 전략 수립 및 브랜치 관리 방안 표준화를 통한 코드 개발 효율성 향상
- CI/CD 파이프라인 구축 및 고도화
	- IaC에 Github Actions 도입, 코드 자동 검증 및 배포 파이프라인 구축, Webhook 연동 업무 수행
	- 주요 워크플로우 모듈화 및 재사용성 개선, 의존성 관리
	- 배포 환경 구분을 위한 environment 전략 활용 및 접근 제어 구성
	- 온프레미스 self hosted runner 운영 및 유지보수, ARC 구성을 통한 러너 자동 스케일링 및 최적화
	- Staging, Production 환경의 배포 검증 시간 95% 이상 감소, 배포 시간 60% 이상 감소
- 클라우드 모니터링 서비스 개발
	- Filebeat, ELK 스택을 이용한 공공클라우드 환경의 로그 모니터링 시스템 구축
	- 외부 CSP(AWS, KT Cloud) 기반의 모니터링 시스템 구축 및 이중화, icingabeat + ELK 스택으로 운영 안정성 지표 데이터화
	- Django 웹 프레임워크로 통합 모니터링 시스템 개발
	- 알림 구조 개선 및 채널 단일화로 운영 효율성 향상
- 운영 도구 개발 및 인프라 개선 (컨테이너화)
	- Openstack 컴포넌트의 메세지 큐(RabbitMQ) 상태 모니터링을 통한 서비스 안정성 확보
	- Openstack SDK를 활용한 주요 컴포넌트 (Nova, Neutron, Cinder) 상태 모니터링 시스템 개발
	- 고객과 동일한 환경에서 모니터링할 수 있는 더미 인스턴스 생성 및 운영 자동화, 서비스 지표로 활용해 운영 안정성 향상
	- Terraform, 사내 메신저를 연동한 배포 후 IaaS 검증 자동화로 배포 업무 효율 증대
	- 레거시 환경 운영 도구들의 컨테이너화 및 Kubernetes 마이그레이션
- Debian apt 패키징 및 빌드 파이프라인 자동화
	- 내부 시스템 배포를 위한 debian 패키지 빌드 및 의존성 패키지 관리
	- Jenkins 파이프라인을 이용한 Git 태그 기반 패키지 빌드, 릴리즈 자동화
### NHN
> System Engineer (intern)
> 2020.01. - 2020.06
- IDC 물리 인프라 구조 학습 및 운영도구 개발
	- 데이터센터 내 서버 랙 구성, 네트워크 배선, 공조 장치 등 물리 인프라 구조 학습
	- 하드웨어(서버/디스크/NIC) 등 IDC의 자산 관리 및 예약을 위한 Django, Javascript 기반의 웹서비스 개발
- Linux 시스템 학습 및 Openstack 인프라 개발환경 구축
	- PXE, DHCP, TFTP, Kickstart를 이용한 원격 인프라 구성 경험
	- DevStack을 활용한 Openstack 테스트 클러스터 구축 및 컴포넌트 간 상호작용 구조 이해
	- Openstack CLI 및 Horizon을 활용한 자원 관리 실습 경험 
### Define
> Researcher (intern)
> 2019.03. - 2019.08
- 머신러닝 기반 비데이터 분류 및 라벨링
	- 정부 연구과제 수주 기업에서 ML 엔진에 사용할 입력 데이터 전처리 업무 수행
	- 이미지 데이터셋 처리 자동화 작업을 위한 python 스크립트 개발 및 유지보수 경험
- 웹 풀스택 및 모바일 앱 개발
	- Javascript, Ajax, Node.js 기반의 웹서버 개발 및 RESTful API 구조 설계
	- stream 모듈을 활용한 실시간 비디오 데이터 시각화 기능 개발
	- 웹서버 기반의 서비스를 Android 앱으로 제공
## 🚀 Project
(프로젝트 제목을 클릭하면 상세 내용을 확인할 수 있습니다!)
### [[AC DC]]

> [!example] Auto Check for Deployment Code (AC/DC)
> 프로젝트 기간: 2023.09 ~ 2025.05
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
> 기술 스택: `fastapi`,  `kubernetes`,  `python`

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
### KyungHee Univ.
> 경희대학교 컴퓨터공학과 (학사)
> 2013.03. - 2020.08
### Qualifications
- Red Hat Certified System Administrator (RHCSA) v8
### Game Development
> Developer, Project Manager
> 2017.01. - 2017.12
> 2024.01. - 현재
- Unity 기반의 게임 개발 프로젝트 리딩
- 인게임 리소스 효율화를 위한 AWS 리소스 연동 및 Terraform IaC 기반의 구성 자동화
- Google sheets 기반의 인게임 맵 데이터 관리 및 에디터 연동 기능 개발
- 3번의 글로벌 게임잼 참여
### Presentation
- [오픈 인프라 서밋 후기](https://2023.openinfradays.kr/session/68) at OpenInfra Community Days Korea 2023
- [NHN Cloud Openstack의 multi-region 배포 전략](https://2025.openinfradays.kr/session/13) at OpenInfra Days Korea 2025
## 📞 Contact
Email. yunbum.han@gmail.com
Github. https://github.com/han-yunb
Linkedin. https://www.linkedin.com/in/yunbumhan
