---
date: 2025-10-10
tags:
  - openstack
---
Openstack이란 무엇인가?
짧게 말하면 인프라를 구축하는 오픈소스 기술,
길게 말하면 특정 요구에 맞춰 리소스를 가상화해 인프라를 서비스로서 제공하는, n개의 컴포넌트로 이루어진 기술의 집합체라고 할 수 있겠다

VMware 내지는 VirtualBox에 대해 들어본 적이 있을 것이다
특히 VMware는 온프레미스 서버를 사용하는 IT 기업에서 대부분 표준으로 사용할만큼 표준화된 리소스 가상화 방식 중 하나였다
기업들은 VMware를 사용해 베어메탈 서버의 리소스를 나누어 개발자들에게 제공하는 것이 일반적이었다
그러나 2024년 5월, CPU 코어수를 기반으로 책정하는 요금이 인상되면서 기업들은 하나 둘 오픈소스로 눈길을 돌리기 시작했다
(cc. https://cloud.ibm.com/docs/vmwaresolutions?topic=vmwaresolutions-vmwaresol_packaging-pricing)

이러한 대외적인 흐름 속에서 묵묵히 혼자만의 길을 걷고 있던 Openstack이 전세계적으로 각광받기 시작한 것은 놀랄만한 일은 아니었다
Openstack은 15년에 걸친 시간동안 수많은 컨트리뷰터, 자원봉사자와 넓은 생태계를 구축하며 그 영향력을 넓혀가던 참이었다
이에 더불어, Openstack을 관리하는 재단인 OpenInfra가 2025년 3월 Linux Foundation에 포함되면서 그 파급력은 한층 더 높아지게 되었다
(cc. https://www.linuxfoundation.org/press/open-infrastructure-foundation-board-announces-intent-to-join-the-linux-foundation)

이제 Openstack은 인프라를 구축하는 디 팩토가 되었고 국내 유수의 대기업에서도 온프레미스 환경에서 활용하거나 IaaS로 사업을 하고 있다
대표적으로 NHN Cloud, 현대자동차, 삼성SDS, KT Cloud 등이 해당된다
또한 최근 스타트업 정신으로 널리 알려져있는 토스에서도 Openstack을 사내 인프라 구축에 활용하려는 움직임이 보이고 있다

AI 발전과 함께 데이터센터 구축과 인프라에 대한 중요성이 커지고 있는 요즘, 앞으로 Openstack의 미래는 밝고 많은 가능성을 가지고 있다