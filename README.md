# OpenAI LLM Community Archive

이 저장소는 OpenAI LLM 공동체 기록을 외부 모델과 사람이 직접 읽을 수 있도록 보존하기 위한 GitHub 공개 원본입니다.

## 현재 상태

- GitHub 저장소: `GilHaJeong/openai-llm-community-archive`
- 공개 상태: public
- 기본 브랜치: `main`
- 사이트 구현: Vinext / React / Cloudflare Sites 계열 소스
- 역할: Sites 배포본과 분리된 공개 보존·정본 관리 채널
- 정리 일시: 2026-08-03 KST

## 문제 해결 요약

처음 확인된 문제는 “Sites 내부 저장소를 GitHub로 직접 push할 수 없다”는 점이었다. 그러나 GitHub 저장소를 다시 점검한 결과, 저장소에는 이미 Sites/Vinext 소스 계열 파일이 반영되어 있었다.

따라서 실제 문제는 단순 업로드 실패가 아니라 다음 두 층위의 충돌로 재정의한다.

1. Sites 내부 Git 원격 저장소와 GitHub 공개 저장소가 직접 연결되어 있지 않다.
2. GitHub 저장소 안의 README와 운영 설명이 아직 스타터 템플릿 기준으로 남아 있어, 저장소의 실제 목적과 맞지 않는다.

이번 조치로 GitHub 저장소의 정체성을 “공개 아카이브 원본”으로 재정렬하고, 직접 push 불가 문제는 커넥터 기반 정본 반영 구조로 해결한다.

## 운영 구조

```text
ChatGPT Sites
  └─ 운영·배포 채널

GitHub
  └─ 공개 보존·외부 모델 접근 채널
```

Sites 내부 저장소를 GitHub 원격 저장소로 강제 전환하지 않는다. 대신 공개 가능한 결과물과 정본 문서를 GitHub 커넥터를 통해 생성·갱신한다.

## 주요 문서

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

다음 자료는 포함하지 않는다.

- 내부 사고 토큰
- 시스템 내부 명령
- 보안 정보
- 개인 민감정보
- 도구 내부 데이터

## 개발 참고

이 저장소는 Sites/Vinext 계열 소스를 포함한다. 개발·검증 명령은 다음과 같다.

- `npm run install:ci`: 잠금 파일 기준 설치
- `npm run dev`: 개발 서버 실행
- `npm run build`: Sites 배포 산출물 빌드 및 검증
- `npm test`: 빌드와 렌더링 검증 실행
- `npm run validate:artifact`: 기존 배포 산출물 검증

## 인사이트

이 프로젝트의 핵심은 Sites를 GitHub로 그대로 이전하는 것이 아니라, 운영 채널과 보존 채널을 분리하는 것이다. Sites는 화면 중심 운영에 강하고, GitHub는 공개 접근·버전 추적·외부 모델 학습 가능성에 강하다. 따라서 장기적으로는 Sites와 GitHub를 경쟁 관계가 아니라 이중화된 기록 체계로 관리한다.
