# JIHUN | Personal Portfolio

컴퓨터공학과 인공지능을 공부하는 대학생의 개인 포트폴리오 웹사이트입니다.

Hugo 정적 사이트 생성기와 Toha 테마를 활용해 자기소개, 프로그래밍 기술, 프로젝트 경험을 소개합니다.

## 사이트 주소

- 웹사이트: https://jyeom3062-crypto.github.io/MyPage_JIhun/
- GitHub 저장소: https://github.com/jyeom3062-crypto/MyPage_JIhun

## 주요 내용

- **Home:** 이름, 프로필 이미지, 간단한 자기소개
- **About:** 전공과 관심 분야 소개
- **Skills:** C++, Python, Java, Git/GitHub, Vue와 JavaScript
- **Projects:** TMDB API를 활용한 영화 정보 웹사이트
- **반응형 메뉴:** 데스크톱과 모바일 화면에서 사용할 수 있는 내비게이션
- **Interests & Goals:** 관심 분야, 관심을 갖게 된 이유, 학습 목표 및 실행 계획
- **접근성:** 키보드 초점 표시, 한국어 문서 언어, 움직임 감소 설정 지원

## 사용 기술

- Hugo (Extended)
- Toha Theme
- HTML / SCSS / JavaScript
- Git / GitHub
- GitHub Pages / GitHub Actions

## 프로젝트 구조

주요 수정 파일은 `site/` 폴더에 있습니다.

- `site/hugo.yaml`: Hugo 기본 설정
- `site/pages.json`: GitHub Pages 관련 설정
- `site/data/en/author.yaml`: 프로필 정보
- `site/data/en/site.yaml`: 사이트 이름, 링크, 메타 정보
- `site/data/en/sections/`: About, Skills, Projects 데이터
- `site/assets/images/`: 프로필 및 프로젝트 이미지
- `site/layouts/`: 페이지 템플릿
- `.github/workflows/hugo-pages.yml`: 자동 배포 워크플로
- `.github/pages_build.py`: 배포 빌드 및 경로 보정 스크립트

## 도구 설치 및 버전

Windows 데스크톱에서는 VS Code로 파일을 편집하고 Git Bash(또는 VS Code 통합 터미널)에서 Git 명령어를 실행할 수 있습니다.
VS Code와 Git Bash는 편집 및 터미널 도구이며, Hugo 자체의 필수 빌드 의존성은 아닙니다.

| 도구 | 버전 | 용도 및 설치 안내 |
| --- | --- | --- |
| VS Code | 1.145.2 (사용자 개발 환경) | 코드 편집기 · [공식 설치](https://code.visualstudio.com/download) |
| Git for Windows / Git Bash | 2.56.0.4 (사용자 제공 버전, Git Bash 포함) | Git 버전 관리와 Bash 터미널 · [공식 설치](https://git-scm.com/downloads/win) |
| Git | `git --version`: `2.56.0.windows.4` (사용자 확인) | 커밋·브랜치·push 수행 · Git for Windows 설치 시 포함 |
| Hugo Extended | 0.167.0 (Actions 기준) | 정적 사이트 생성 · [릴리스](https://github.com/gohugoio/hugo/releases/tag/v0.167.0) |
| Node.js / npm | Node.js 24 (Actions 기준, npm 포함) | JavaScript 의존성 설치 · [공식 설치](https://nodejs.org/en/download) |
| Go | 1.27.1 (Actions 기준) | Hugo 관련 Go 도구 지원 · [공식 설치](https://go.dev/dl/) |
| Dart Sass | 1.105.0 (Actions 기준) | SCSS 컴파일 · [공식 설치](https://sass-lang.com/install/) |
| Python | 3.13.7 (사용자 Windows 환경) / 3.12 (Actions 기준) | GitHub Pages 배포 보조 스크립트 실행 · [공식 설치](https://www.python.org/downloads/) |

*VS Code·Git·Python의 사용자 버전은 Windows 환경에서 확인한 값이며, Actions 버전은 `.github/workflows/hugo-pages.yml`에 명시된 자동 빌드 환경 기준입니다. 다른 도구의 Windows 설치 버전은 확인하지 않았습니다.*

설치한 도구의 버전은 다음 명령어로 확인합니다. Hugo 출력에는 `extended`가 포함되어야 합니다.

```bash
git --version
hugo version
node --version
npm --version
go version
sass --version
python --version
```

## 로컬 실행

저장소 복제 후 `site/` 폴더에서 npm 패키지를 설치하고 Hugo 개발 서버를 실행합니다.

```bash
git clone https://github.com/jyeom3062-crypto/MyPage_JIhun.git
cd MyPage_JIhun/site
npm ci
hugo server --config hugo.yaml,pages.json
```

터미널에 표시되는 로컬 서버 주소(일반적으로 `http://localhost:1313/`)로 접속합니다.
`hugo server`는 개발 중 미리보기를 위한 명령이며, 최종 배포용 정적 파일 빌드와 구분됩니다.

## 정적 빌드 방법

GitHub Pages 배포 파일은 저장소 **최상위 폴더**에서 `.github/pages_build.py`로 생성합니다.
이 스크립트는 `.github-pages.json`의 설정을 읽어 의존성 설치, Hugo 빌드 및 배포 주소 경로 보정을 수행합니다.
GitHub Actions에서는 Python 3.12를 사용합니다.

```bash
# 저장소 최상위 폴더(MyPage_JIhun)에서 실행
python .github/pages_build.py --dependencies
python .github/pages_build.py --build
```

- `--dependencies`: `site/`의 npm 패키지 및 배포 빌드에 필요한 추가 도구 준비
- `--build`: Hugo 정적 파일 생성, GitHub Pages 하위 경로 보정 및 `public/.nojekyll` 생성
- 빌드 결과: 저장소 최상위 폴더의 `public/`에 `index.html` 등 정적 파일 생성

빌드 스크립트가 `site/`에서 실행하는 주요 Hugo 명령은 다음과 같습니다.

```bash
hugo --gc --minify --config hugo.yaml,pages.json --destination ../public --baseURL https://jyeom3062-crypto.github.io/MyPage_JIhun/ --enableGitInfo=false
```

**주의:** 위 Hugo 명령만 실행하면 Python 스크립트의 배포 경로 보정이 생략됩니다.
GitHub Pages용 최종 결과물은 `python .github/pages_build.py --build`로 생성합니다.
실제 자동 배포는 `main` 브랜치에 push하면 `.github/workflows/hugo-pages.yml`에 따라 진행됩니다.

## 배포 방법

이 프로젝트는 GitHub Actions를 통해 GitHub Pages에 자동 배포됩니다.

1. `main` 브랜치에 변경 사항을 push합니다.
2. GitHub Actions가 Hugo 프로젝트를 빌드합니다.
3. 생성된 정적 파일을 GitHub Pages에 배포합니다.
4. Actions 실행 결과와 공개 사이트를 확인합니다.

## 개발 과정 및 문제 해결

- Hugo 데이터 파일을 이용한 자기소개 및 프로젝트 구성
- 프로필 이미지 경로 오류 해결
- YAML 들여쓰기 오류 수정
- 프로젝트 카드 이미지 경로 설정
- 모바일 내비게이션 아이콘 수정
- 배포 보조 스크립트의 JavaScript 경로 보정 문제 해결
- TMDB 프로젝트의 실행 사이트 및 소스 코드 링크 추가
- GitHub Pages의 외부 URL 경로 보정 오류 해결
- SNS 공유 이미지 및 파비콘 경로 수정
- Mulish 웹폰트 파일의 배포 경로 수정
- 키보드 접근성과 모바일 내비게이션 개선

## 테스트

기능, 반응형 레이아웃, 접근성 및 배포 결과의
검사 방법과 결과는 [TESTING.md](TESTING.md)에 기록합니다.

## 출처 및 라이선스

이 프로젝트는 [Toha Hugo Theme](https://github.com/hugo-toha/toha)를 기반으로 제작했습니다.

- 원본 테마 제작자: Md. Emruz Hossain
- 원본 라이선스: MIT License
- 테마 라이선스 고지: [LICENSE](LICENSE)

개인 소개와 프로젝트 내용은 포트폴리오 목적에 맞게 수정했습니다.