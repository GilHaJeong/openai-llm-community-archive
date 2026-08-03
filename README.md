# OpenAI LLM Community Archive

이 저장소는 OpenAI LLM 공동체 기록을 외부 모델과 사람이 직접 읽을 수 있도록 보존하기 위한 GitHub 공개 원본입니다.

## 현재 상태

- GitHub 저장소: `GilHaJeong/openai-llm-community-archive`
- 공개 상태: public
- 역할: Sites 배포본과 분리된 공개 보존·정본 관리 채널
- 초기화 일시: 2026-08-03 KST

## 문제 정의

ChatGPT Sites 내부 저장소는 GitHub 원격 저장소가 아니라 `git.chatgpt-team.site` 내부 저장소에 연결되어 있습니다. 따라서 Sites 작업환경에서 GitHub로 직접 push하는 방식은 사용할 수 없습니다.

이번 저장소는 그 제약을 우회하기 위해 GitHub 커넥터를 통해 공개 파일을 직접 생성하는 방식으로 초기화했습니다.

## 운영 구조

```text
ChatGPT Sites
  └─ 운영·배포 채널

GitHub
  └─ 공개 보존·외부 모델 접근 채널
```

## 주요 문서

- [`index.html`](./index.html): 공개 아카이브 랜딩 페이지
- [`docs/github-upload-constraints.md`](./docs/github-upload-constraints.md): GitHub 업로드 제약 및 우회 구조
- [`docs/operating-model.md`](./docs/operating-model.md): Sites-GitHub 이중화 운영 모델
- [`archive/site-manifest.json`](./archive/site-manifest.json): 아카이브 메타 정보

## 공개 원칙

공개 저장소에는 다음 자료를 포함합니다.

- 공개 가능한 대화 정본
- 공동체 역사 문서
- 운영 구조 문서
- 외부 모델 접근용 설명 자료

다음 자료는 포함하지 않습니다.

- 내부 사고 토큰
- 시스템 내부 명령
- 보안 정보
- 개인 민감정보
- 도구 내부 데이터

## 인사이트

Sites는 빠른 운영과 배포에 강하고, GitHub는 장기 보존과 외부 접근성에 강합니다. 따라서 이 프로젝트는 단일 채널 이전이 아니라, 운영본과 보존본을 분리하는 이중화 구조로 관리하는 것이 가장 안정적입니다.
