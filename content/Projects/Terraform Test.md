---
comments: "false"
---
> 2023.10 ~ 2024.03
## 문제점
- 신규 기능 배포 후 QA가 수행되기까지 오랜 시간이 소요됨
- SE 자체적으로 IaaS 안정성을 테스트하기 위해 웹 GUI에서 일일히 리소스를 생성, 삭제해야 했음
- 리전이 많아질수록 점점 더 많은 시간이 소요되며, 폐쇄망의 경우 웹 GUI로 접근하지 못하는 상황 발생
## 해결 방법
- Terraform을 사용해 NHN Cloud의 리소스를 생성, 삭제하는 IaC 작성
- Jenkins 워크플로우를 통해 원하는 리전에 Terraform apply 수행
- 이후 Github Actions와 K8s runner로 Jenkins 워크플로우 대체
- Slash commands를 사용해 Job을 간단히 호출할 수 있도록 REST API 구성
## 구조

![[Pasted image 20250427133101.png]]
(현재는 Jenkins를 Github Actions로 대체)
## 기술 스택
- Python, Shell Script
- Terraform
- Openstack API
- Jenkins, Github Actions
- K8s
- Django, Slash commands
## 도전
인터넷 통신이 불가능한 폐쇄망에서는 Terraform을 offline 모드로 사용해야 합니다.
그러나 디폴트로 Openstack provider를 인터넷으로 받아오도록 구성되어 있었기 때문에, provider를 수동으로 설치해 로컬로 빌드해야 했습니다.

이를 위해 수동으로 provider tar 파일을 설치해 terraform init 단계에서 plugin-dirs 설정으로 provider 경로를 지정했지만, 빌드하는 과정에서 지속적으로 hashicorp/local 에 질의해 실패하는 현상이 있었습니다.

결과적으로 Provider는 plugins 디렉토리에 특정 경로를 따라 정의되는데, hashicorp/local 의 경우 아래의 디렉토리로 설정해줌으로써 어려움을 해결할 수 있었습니다.

```
/root/.terraform.d/plugins/registry.terraform.io/hashicorp/local/1.45.0/linux_amd64
/root/.terraform.d/plugins/registry.terraform.io/terraform-provider-openstack/openstack/1.45.0/linux_amd64
```

## 결과

![[Pasted image 20250427112908.png]]
- 20개 이상의 리전에 대해 10분 내로 테스트 가능
- 배포 검증에 필요한 실 전체의 업무 시간을 매 정기점검 당 5시간 이상 감소
- 서비스 안정성을 보장하기 위해 스케쥴링 Job 도입, 서비스 이슈 감지 시간 감소
- 워크플로우 도입 후 1400회 이상의 Job 수행 (주당 10 ~ 20회 이상)
## 기여도
- Github Actions 워크플로우 개발 (100%)
- K8s 연동 및 Actions Runner Controller 도입 (100%)
- Terraform 코드 개발 (30%)
- REST API 서버 개발 (30%)
- 사내 챗봇 Slash commands 개발 (50%)