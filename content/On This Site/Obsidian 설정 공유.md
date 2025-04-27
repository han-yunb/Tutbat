## .gitignore

개인 vault 에서는 PARA 방식을 사용하지만 블로그로 운영하는 vault 에서는 제텔카스텐 방식을 사용해볼 예정이다
제텔카스텐은 어떤 아이디어가 떠올랐을 때 간단히 메모해두고 평소 기록해둔 리소스를 활용해 하나의 글을 발행하는 방식이다
아직 미완성의 글을 발행할 수 없으므로 `content/private/` 하위 디렉토리는 ignore 한다

```shell title=".gitignore"
content/private/
```

→ quartz 에서 default로 private 하위 문서는 빌드에 포함하지 않는다

## 커스텀 도메인

cloudflare에서 호스팅하면 웹페이지 도메인 상태가 영 예쁘지 않으므로 커스텀 도메인으로 변경한다
메인 도메인은 정원을 가꾸는 gardener 처럼 텃밭을 가꾸는 `tutbater.com` 으로 결정
블로그는 `digital.tutbater.com` 서브도메인으로 구성한다

## 프론트엔드 가공

```typescript title="quartz.config.ts"
pageTitle: "Digital Tutbat",
analytics: null,
baseUrl: "digital.tutbater.com"

Plugin.HardLineBreaks() // 플러그인 추가
```

```typescript title="quartz.layout.ts"
Github: "https://github.com/han-yunb/Tutbat"
```

```text title="quartz/components/Footer.tsx"
- Linkedin 프로필 링크 추가
```

```css title="quartz/styles/custom.scss"
body, section {
  font-size: 18px;
}
article h2 {
  font-size: 25px;
}
article h3 {
  font-size: 22px;
}
```


## 댓글 설정
Giscus provider를 사용해서 댓글을 달 수 있도록 설정할 수 있다 (단, public repo만 가능)
자세한 내용은 아래 링크 참고
> https://quartz.jzhao.xyz/features/comments

# 트러블슈팅

## 사이드바 중복 이슈

다른 노트는 괜찮은데, 자기소개 노트인 `About Me` 에서만 자꾸 사이드바가 중복으로 생기는 이슈가 있었다
디버깅을 해봤는데 결과적으로 cloudflare에서 이메일 주소를 막는 기능 때문이었다

Scrape Shield 탭에서 Email Address Obfuscation 모드를 disable 하니 해결되었다
해당 모드를 키면 웹페이지를 로드할 때 Javascript를 수행하는 것 같은데, Obsidian과 호환되지 않아 이슈를 발생시키는 것으로 추측된다

