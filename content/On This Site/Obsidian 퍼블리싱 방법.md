[[디지털 텃밭]]을 퍼블리싱하기 위한 실질적인 방법론을 정리
방법 중 하나로, [[Quartz 빌드]]를 이용하면 Obsidian의 내용을 그대로 퍼블리싱할 수 있다
### Cloudflare
호스팅 플랫폼은 크게 두 개로 좁힐 수 있다
github pages와 cloudflare pages가 그것인데, 둘 다 무료로 사용할 수 있다는 점에서 접근성이 좋다
세부적인 부분은 조금씩 다르지만, Cloudflare의 무제한 대역폭과 빠른 로딩 성능이 블로깅에 장점이 있다고 생각한다

- Github Pages
	- 빌드 제한 없음
	- 커스텀 빌드 파이프라인 개발 가능
- Cloudflare Pages
	- 무제한 대역폭, CDN
	- 빠른 로딩 성능
	- 간편한 빌드 시스템 (git 연동)
## 퍼블리싱 방법
### Cloudflare에 Github 연동

Git 계정이 연동되어 있다면 Application 생성 창에서 import 할 repo를 선택할 수 있다
(Git을 연동하기 위해서는 Cloudflare Github App을 Application에 추가하고 접근할 repo를 선택하면 된다)
repo를 선택하면 어떤 branch를 배포할 것인지 선택할 수 있고, `Deploy command` 부분에 obsidian 빌드 명령어만 명시해주면 된다

```shell
npx wrangler deploy
```
> https://developers.cloudflare.com/workers/ci-cd/builds/