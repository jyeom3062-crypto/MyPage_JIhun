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

## 로컬 실행

필요한 개발 환경:

- Hugo Extended 0.167.0
- Node.js 및 npm
- Go
- Dart Sass

저장소를 복제한 뒤 `site` 폴더에서 의존성을 설치합니다.

```bash
cd site
npm ci
hugo server --config hugo.yaml,pages.json
```

터미널에 표시되는 로컬 서버 주소로 접속합니다.

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