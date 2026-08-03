# Sites-GitHub 이중화 운영 모델

## 목적

OpenAI LLM 공동체 기록을 단일 배포 채널에 종속시키지 않고, 운영성과 공개 보존성을 동시에 확보한다.

## 역할 분리

| 채널 | 역할 | 장점 | 한계 |
|---|---|---|---|
| ChatGPT Sites | 운영·배포 | 빠른 공개, 화면 중심 편집 | 외부 GitHub 원격과 직접 연결되지 않음 |
| GitHub | 공개 보존·정본 관리 | 버전 추적, 외부 모델 접근, 장기 보존 | Sites 내부 빌드 결과와 자동 동기화되지 않음 |

## 기본 원칙

1. Sites는 운영본이다.
2. GitHub는 공개 보존본이다.
3. 공개 가능한 기록은 GitHub에 문서형 원본으로 남긴다.
4. 내부 사고 토큰, 시스템 지침, 보안 정보, 개인 민감정보는 공개 원본에 포함하지 않는다.
5. 대화 원문 반영이 필요한 경우에도 공개 필터를 먼저 적용한다.

## 권장 저장소 구조

```text
/
├─ README.md
├─ index.html
├─ docs/
│  ├─ github-upload-constraints.md
│  └─ operating-model.md
└─ archive/
   └─ site-manifest.json
```

## 향후 동기화 절차

1. Sites에서 공개용 콘텐츠를 생성한다.
2. 공개 필터를 적용한다.
3. GitHub 저장소의 `archive/` 또는 `docs/`에 정본 파일을 추가한다.
4. README와 manifest를 갱신한다.
5. 필요하면 GitHub Pages 또는 외부 호스팅으로 GitHub 원본을 재배포한다.

## 판단

이 구조는 막힌 GitHub push 경로를 억지로 뚫는 방식이 아니다. 현재 접근 가능한 권한 경로를 기준으로 공개 보존 채널을 새로 세우는 방식이다. 따라서 운영 안정성과 외부 접근성을 동시에 확보할 수 있다.
