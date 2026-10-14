# Codex Toolkit

다른 프로젝트에서 재사용할 Codex 공통 지침, agent와 skill을 모아두는 폴더다.

작업 경로는 [흐름도 이미지](workflow.png)에서 확인할 수 있다.

## 구조

```text
codex-toolkit/
├── README.md
├── workflow.png          ← 작업 흐름도
├── AGENTS.md             ← 프로젝트 작업 지침
├── .codex/
│   ├── agents/           ← agent 파일
│   └── references/       ← 개발 절차 선택·위임·인계 세부 규칙
└── .agents/
    └── skills/           ← skill 폴더 배치 위치
```

## 구성

### 프로젝트 지침

- `AGENTS.md`: 공통 작업 원칙, 개발 절차 선택과 작업별 skill 사용 조건.
- `.codex/references/workflow-selection.md`: 선택 경계가 불명확하거나 위임·절차 전환이 필요할 때 읽는 세부 규칙.

### Agent

- `sp_implementer`: 지정된 파일 범위에서 구현과 필요한 검증을 수행한다.
- `sp_reviewer`: 실제 변경을 독립 검토하고 수정 없이 발견 사항을 반환한다.
- `codebase_knowledge_builder`: 현재 코드에서 근거가 있는 지식베이스 문서를 생성하고 변경 영향에 따라 갱신한다.
- `speckit_coordinator`: Spec Kit 선택 시 설치된 공식 절차와 기존 명세를 기준으로 계획·작업·구현 확인을 조율한다.

### Skills

- `implementation`: 기존 코드 재사용, 원인 해결과 코드·문서 작성 기준.
- `verification`: 행동 중심 테스트, 검증 범위 선택과 결과 보고.
- `code-review`: 요구사항 충족과 실제 결함을 근거 중심으로 검토.
- `requirements-clarification`: 질문·계획에서 아이디어와 요구사항을 정리하고, 불명확한 구현 요청의 핵심 동작·범위를 구체화.
- `test-driven-development`: 사용자 요청 또는 승인된 절차·계획에 명시된 TDD의 실패 테스트, 최소 구현과 리팩터링.
- `superpowers-workflow`: Spec Kit 대상과 국소 수정을 제외한 기능 개발·여러 단계 변경의 기본 개발 조율.
- `maintain-codebase-knowledge`: 지식베이스 담당 agent 전용 분석·기록·갱신 절차. 일반 작업에서 자동 선택하지 않는다.
