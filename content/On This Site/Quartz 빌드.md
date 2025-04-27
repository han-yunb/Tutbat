> based on: Quartz 4.4

정적 웹사이트 생성기인 quartz는 [[Obsidian 퍼블리싱 방법]] 중 하나로, 오픈소스로 공개되어 있다 (자세한 사항은 [quartz documentation](https://quartz.jzhao.xyz/)을 참고)
본 문서에서는 간단한 Quartz 빌드 방법 뿐만 아니라, 사용한 기능들에 대해서도 기록한다

## 환경 설정

> macOS: 15.3.2
> python: 3.12.3

빌드 서버를 일관성있게 유지하기 위해 가상환경 기반으로 설정해준다

```shell
python3 -m venv tutbat
cd tutbat
source bin/activate
```
## 빌드

> npm: 10.5.1

quartz를 설치하고 빌드해본다

```shell
git clone https://github.com/jackyzha0/quartz.git
cd quartz
npm i
npx quartz create
```

## 동기화

노트를 여러 기기에서 조회하고 작성하려면 동기화가 필수적이다
Obsidian 에서 공식적으로 지원하는 Sync 플러그인은 유료이므로 iCloud를 이용해서 동기화하도록 설정한다
→ 단지 vault를 iCloud 디렉토리에 옮기기만 하면 된다. 끝!

참고로 터미널에서 iCloud에 접근하기 위해서 아래 경로를 사용한다
```shell
/Users/${user-id}/Library/Mobile\ Documents/iCloud~md~obsidian/Documents/${vault-name}
```

개인적으로 가상환경은 iCloud가 아닌 로컬 드라이브에 올려두었는데, 매번 빌드할 때마다 iCloud 경로로 이동하는 것이 번거로워 심볼릭 링크를 걸어두었다

```shell title="~/work/quartz"
ln -s ${icloud 절대경로} ${상대경로}
```
## 플러그인

후술할 호스팅을 위해서는 github 연동이 필요한데, Obsidian 플러그인을 사용하면 간단하게 처리할 수 있다
Private 레포로 진행해도 무방하지만 어차피 공개 블로그 목적으로 관리할거라 Public 레포로 만들어주었다
나는 quartz를 clone해서 사용했기 때문에 remote repo 정보를 바꿔줄 것이다 (처음에 fork해도 무방)

```shell
git remote remove origin
git remote add origin ${github-repository-url}
git branch -M master
```

이후 내용을 한 번 push 해준다
