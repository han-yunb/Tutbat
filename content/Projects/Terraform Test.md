---
comments: "false"
---
> 2023.10 ~ 2024.03
## 문제점
- Public Cloud에 신규 기능 배포 후 QA가 수행되기까지 오랜 시간이 소요됨
- QA 결과가 공유되기 전에 시스템 엔지니어는 자체적으로 클라우드 안정성을 테스트
- 콘솔 화면에서 일일히 리소스를 생성, 테스트 후 삭제하는 반복적인 작업을 수행해야 했음
- 리전이 많아질수록 점점 더 많은 시간이 소요되었고, 이 작업을 자동화하기로 결정
## 해결 방법
- Terraform을 사용해 NHN Cloud의 리소스를 생성, 테스트, 삭제하는 코드 작성
- Jenkins 워크플로우를 통해 원하는 리전에 Terraform apply 수행
- 사용자가 손쉽게 테스트할 수 있도록 챗봇 Slash command를 개발해 제공
## 구조

![[Pasted image 20250427133101.png]]
(현재는 Jenkins를 Github Actions로 대체)
## 기술 스택
- Python, Shell Script
- Terraform
- Openstack API
- Jenkins, Github Actions
- K8s
- Django
## 도전
Jenkins 파이프라인을 Github Actions로 옮기는 것이 가장 큰 도전이었습니다.
기존 방식으로 사용해도 문제가 없는 시스템을 효율성을 향상시키기 위한 목적으로 도전할 때, 대부분의 사람들은 불필요한 작업이 아닌지 의심의 눈초리를 보내게 됩니다.

하지만 사내 규정상 Jenkins는 동시에 5개 이상의 Job을 수행할 수 없고, 일부 리전은 아예 통신이 불가능해 별도의 Jenkins 서버를 운영해야하는 단점이 있었습니다.
이에 반해 Github Actions는 통신 구간이 비교적 자유로웠고 Kubernetes를 연동하면 요청에 따라 Runner Pod을 생성해 동시에 모든 리전을 테스트할 수 있을 것으로 기대했습니다.

결과적으로 제 예상은 맞아떨어졌고 Actions Runner Controller (ARC)를 활용해 Runner Pod을 동적으로 생성할 수 있게 되었습니다. 이를 통해 Jenkins를 사용하는 것 대비 최대 75%의 시간을 절감할 수 있었습니다.
## 결과
- 20개 이상의 리전에 대해 10분 내로 기본 인프라 서비스 테스트 가능
	- 인스턴스 생성, Load Balancer 생성 및 인스턴스 멤버 추가, 공인 IP로 통신 확인
- 배포 검증에 필요한 실 전체의 업무 시간을 매 정기점검 당 5시간 이상 감소
- 배포 작업에만 사용하는 것이 아니라 매일 서비스를 검증하는 데 사용하도록 용도 확대
	- 서비스 이슈 감지까지 걸리는 시간 감소
- 워크플로우 도입 후 1400회 이상의 Job 수행 (주당 10 ~ 20회 이상)
## 기여도
- Github Actions 워크플로우 개발 (100%)
	- 공공, 폐쇄망 환경 등 복합적인 리전도 한 번의 워크플로우로 처리할 수 있도록 개발
	- Schedule Job 기능으로 매일 오전에 전체적인 서비스를 검증하도록 구성
- K8s 연동 및 Actions Runner Controller 도입 (100%)
	- Terraform 모듈을 포함한 커스텀 이미지를 빌드해 Runner Pod 생성
- Terraform 코드 개발 (30%)
	- Openstack provider를 활용해 NHN Cloud 리소스를 생성할 수 있도록 개발
	- 폐쇄망에서도 테스트할 수 있도록 Local provider 구성
- REST API 서버 개발 (30%)
	- 메세지 슬래시 커맨드, 웹훅 등 요청을 받고 결과를 리턴하기 위한 Django 서버 개발