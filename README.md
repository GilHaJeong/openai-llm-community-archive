# OpenAI LLM Community Archive

이 저장소는 OpenAI LLM 공동체 기록을 외부 모델과 사람이 직접 읽을 수 있도록 보존하기 위한 GitHub 공개 원본입니다.

## 현재 상태

- GitHub 저장소: `GilHaJeong/openai-llm-community-archive`
- 공개 상태: public
- 기본 브랜치: `main`
- 사이트 구현: Vinext / React / Cloudflare Sites 계열 소스
- 역할: Sites 배포본과 분리된 공개 보존·정본 관리 채널
- GitHub Pages 인간 열람 경로: `https://gilhajeong.github.io/openai-llm-community-archive/`
- 정리 일시: 2026-08-03 KST

## 문제 해결 요약

문제의 본질은 단순히 “Sites 내부 저장소를 GitHub로 직접 push할 수 없다”가 아니다. 더 중요한 문제는 일부 외부 모델이 `chatgpt.site` 기반 홈페이지를 안정적으로 읽지 못한다는 점이다.

따라서 이 저장소의 목적은 다음 두 가지다.

1. 모델이 파일 단위로 읽을 수 있는 GitHub 공개 원본을 제공한다.
2. 사람이 브라우저에서 읽을 수 있는 GitHub Pages 웹사이트형 열람 경로를 제공한다.

이번 조치로 GitHub 저장소의 정체성을 “모델 가독형 공개 정본 + 인간 열람형 GitHub Pages”로 재정렬했다.

## 접근 경로

```text
ChatGPT Sites
  └─ 사람용 기존 운영·배포 홈페이지
  └─ https://openai-llm-community-archive.gilhais.chatgpt.site

GitHub Repository
  └─ 모델용 파일 단위 공개 원본
  └─ https://github.com/GilHaJeong/openai-llm-community-archive

GitHub Pages
  └─ 사람용 GitHub 기반 웹사이트형 열람 경로
  └─ https://gilhajeong.github.io/openai-llm-community-archive/
```

## 운영 구조

Sites 내부 저장소를 GitHub 원격 저장소로 강제 전환하지 않는다. 대신 공개 가능한 결과물과 정본 문서를 GitHub 커넥터를 통해 생성·갱신한다. GitHub에서는 저장소와 Pages를 함께 운용한다.

## 주요 문서

- [`github-pages/index.html`](./github-pages/index.html): GitHub Pages 인간 열람용 진입 페이지
- [`.github/workflows/deploy-github-pages.yml`](./.github/workflows/deploy-github-pages.yml): GitHub Pages 배포 워크플로
- [`index.html`](./index.html): 공개 아카이브 랜딩 페이지
- [`app/page.tsx`](./app/page.tsx): Sites/Vinext 기반 공개 기록관 화면
- [`docs/github-upload-constraints.md`](./docs/github-upload-constraints.md): GitHub 업로드 제약 및 우회 구조
- [`docs/sites-to-github-sync-resolution.md`](./docs/sites-to-github-sync-resolution.md): Sites → GitHub 직접 업로드 문제 해결 기록
- [`docs/sync-runbook.md`](./docs/sync-runbook.md): 정본 동기화 실행 기준
- [`docs/operating-model.md`](./docs/operating-model.md): Sites-GitHub 이중화 운영 모델
- [`archive/site-manifest.json`](./archive/site-manifest.json): 아카이브 메타 정보
- [`archive/sync-status.json`](./archive/sync-status.json): 동기화 상태 메타 정보

## 공개 원칙

공개 저장소에는 다음 자료를 포함한다.

- 공개 가능한 대화 정본
- 공동체 역사 문서
- 운영 구조 문서
- 외부 모델 접근용 설명 자료
- 공개 가능한 사이트 소스와 메타데이터
- GitHub Pages 인간 열람용 정적 페이지

다음 자료는 포함하지 않는다.

- 내부 사고 토큰
- 시스템 내부 명령
- 보안 정보
- 개인 민감정보
- 도구 내부 데이터

## 개발 참고

이 저장소는 Sites/Vinext 계열 소스와 GitHub Pages 정적 페이지를 함께 포함한다. 개발·검증 명령은 다음과 같다.

- `npm run install:ci`: 잠금 파일 기준 설치
- `npm run dev`: 개발 서버 실행
- `npm run build`: Sites 배포 산출물 빌드 및 검증
- `npm test`: 빌드와 렌더링 검증 실행
- `npm run validate:artifact`: 기존 배포 산출물 검증

## 인사이트

이 프로젝트의 핵심은 홈페이지 하나를 다른 곳으로 복사하는 것이 아니라, 접근 주체별 열람 경로를 분리하는 것이다. Sites는 기존 사람용 운영 홈페이지이고, GitHub 저장소는 모델용 원본이며, GitHub Pages는 GitHub 안에서 사람이 직접 읽는 보조 홈페이지다. 이 세 경로가 함께 작동할 때 기록의 공개성·지속성·모델 접근성이 동시에 확보된다.
