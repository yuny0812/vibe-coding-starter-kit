# {{PROJECT_NAME}}

> 한 문장 설명: {{누가 어떤 문제를 해결하기 위해 무엇을 만드는 프로젝트인지 적으세요.}}

이 저장소는 사람은 **무엇을 왜 만들지와 완료 기준을 책임지고**, AI 코딩 에이전트는 정해진 범위 안에서 **분석·계획·구현·검증을 반복**하도록 설계된 풀스택 Vibe Coding Starter Repository입니다.

새 프로젝트라면 가장 먼저 [`START_HERE.md`](START_HERE.md)를 열어 AI 인터뷰를 시작하세요.

기본 구조는 프론트엔드와 백엔드가 분리된 모노레포입니다. 작은 CLI나 단일 서비스는 루트 `src/`를 사용할 수 있지만, 한 프로젝트에서 `src/`와 `apps/`에 같은 책임의 코드를 중복 구현하지 않습니다.

## Project Lifecycle Kit과의 관계

이 저장소는 [`yuny0812/project-lifecycle-kit`](https://github.com/yuny0812/project-lifecycle-kit)의 복사본이 아닙니다. 두 저장소의 책임을 다음처럼 분리합니다.

| 구분 | 보관하는 것 | 갱신 방식 |
|---|---|---|
| Project Lifecycle Kit | 재사용 가능한 기획·구축·검증·운영 방법, 게이트, 체크리스트 | 원본 kit을 한 곳에서 개선 |
| 이 Starter Repository | 개별 프로젝트의 코드, 명세, ADR, 계획, 작업 로그, 검증 증거 | 프로젝트와 함께 변경 |

즉 **방법(method)은 kit에**, **프로젝트별 사례(instance)는 이 저장소에** 둡니다. kit을 설치하지 않아도 이 템플릿만으로 시작할 수 있고, kit을 함께 사용하면 `docs/06_READINESS_GATE.md`와 `process/`의 산출물을 연결합니다.

## 시작 전 사용자가 답해야 할 질문

아래 질문에 답한 뒤 상세 내용을 `docs/`에 옮기세요. 모르는 항목은 지어내지 말고 `TBD`와 결정 예정일을 적습니다.

- 프로젝트 이름과 한 문장 설명은 무엇인가?
- 이 프로젝트가 해결할 가장 중요한 문제는 무엇인가?
- 핵심 사용자는 누구이며, 사용 후 무엇을 할 수 있어야 하는가?
- 첫 릴리스에 반드시 포함할 범위와 명시적으로 제외할 범위는 무엇인가?
- 성공 여부를 판단할 측정 가능한 기준은 무엇인가?
- 기술, 일정, 비용, 보안, 운영상의 제약은 무엇인가?
- 어떤 명령으로 설치, 실행, 테스트, 린트, 빌드하는가?
- 프론트엔드, 백엔드, 공통 계약, 데이터베이스, 인프라에 어떤 기술을 사용할 것인가?
- 화면, API, 배치, 이벤트 등 사용자가 진입하는 모든 지점은 무엇인가?
- 사람이 반드시 승인해야 하는 변경은 무엇인가?

## 15분 시작 순서

1. GitHub에서 이 저장소를 Template Repository로 지정한 뒤 새 프로젝트를 생성합니다.
2. `START_HERE.md`의 시작 프롬프트를 AI 에이전트에게 전달해 질문 인터뷰를 진행합니다.
3. `{{...}}`, `[답변]`, `TBD`를 검색해 아래 문서를 순서대로 완성합니다.
4. `.env.example`을 복사해 로컬 환경 파일을 만들고 실제 비밀값은 커밋하지 않습니다.
5. `process/context/ALL_CONTEXT.md`에서 실제 기술 스택과 코드 위치를 확정합니다.
6. 에이전트가 만든 계획을 `process/plans/active/`에서 확인하고 `docs/06_READINESS_GATE.md`의 V1~V7을 통과한 뒤 구현합니다.

## 문서 작성 순서

| 순서 | 문서 | 결정하는 내용 |
|---:|---|---|
| 1 | [`docs/00_PROJECT_BRIEF.md`](docs/00_PROJECT_BRIEF.md) | 문제, 목표, 사용자, 범위, 제약 |
| 2 | [`docs/01_REQUIREMENTS.md`](docs/01_REQUIREMENTS.md) | 기능·비기능 요구사항과 우선순위 |
| 3 | [`docs/02_ARCHITECTURE.md`](docs/02_ARCHITECTURE.md) | 시스템 경계, 구성요소, 데이터, 외부 연동 |
| 4 | [`docs/03_ACCEPTANCE_CRITERIA.md`](docs/03_ACCEPTANCE_CRITERIA.md) | 검증 가능한 완료 조건 |
| 5 | [`docs/04_CONVENTIONS.md`](docs/04_CONVENTIONS.md) | 명령어, 코딩·테스트·Git 규칙 |
| 6 | [`docs/05_INTERFACE_SPEC.md`](docs/05_INTERFACE_SPEC.md) | 화면, API, 상태, 권한, 오류 계약 |
| 7 | [`docs/06_READINESS_GATE.md`](docs/06_READINESS_GATE.md) | 계획·실행·출시 전 V1~V7 검증 계약 |
| 8 | [`docs/decisions/README.md`](docs/decisions/README.md) | 오래 남을 중요한 결정과 근거 |
| 9 | [`process/README.md`](process/README.md) | Research부터 Closeout까지 작업 라이프사이클 |

## Source of Truth

- 승인된 제품·아키텍처 지식은 `docs/`에 저장합니다.
- 실제 코드베이스의 현재 상태와 경로는 `process/context/`에 저장합니다.
- 진행 중·완료·보류 작업은 `process/plans/`와 `process/features/`에서 관리합니다.
- 테스트·리뷰·수동 확인 증거는 `process/evidence/`에 남깁니다.
- `AGENTS.md`와 `CLAUDE.md`는 프로젝트 지식을 복제하지 않고 어떤 문서를 언제 읽고 어떻게 일할지를 정의합니다.
- 제품 범위가 바뀌면 `00_PROJECT_BRIEF.md`와 요구사항을 먼저 갱신합니다.
- 구조적 결정이 바뀌면 `02_ARCHITECTURE.md`와 ADR을 갱신합니다.
- 완료 기준이 바뀌면 `03_ACCEPTANCE_CRITERIA.md`를 갱신합니다.
- 실행 명령이나 팀 규칙이 바뀌면 `04_CONVENTIONS.md`를 갱신합니다.
- 화면·API·상태·권한 계약이 바뀌면 `05_INTERFACE_SPEC.md`를 갱신합니다.
- 큰 기능은 Research → Spec → Options → Plan → Validate → Execute → Closeout 순서를 따릅니다.
- 작은 저위험 수정은 Quick Fix 경로를 사용할 수 있지만 검증 결과는 생략하지 않습니다.

## 첫 작업 프롬프트

아래 내용을 Codex, Claude Code 또는 다른 코딩 에이전트의 첫 요청으로 사용하세요.

```text
이 저장소의 AGENTS.md를 먼저 읽고 그 지침을 따르세요. CLAUDE.md가 적용되는 환경이면 그것도 읽으세요.

그다음 process/context/ALL_CONTEXT.md를 라우터로 사용해 docs/00_PROJECT_BRIEF.md부터 docs/06_READINESS_GATE.md까지 관련 문서를 검토하세요. 답이 비어 있거나 서로 충돌하거나 구현을 크게 바꿀 수 있는 항목만 질문 목록으로 정리하세요. 합리적으로 가정할 수 있는 사소한 항목은 가정과 근거를 명시하세요.

새 구축 또는 큰 기능이면 process/development-protocols/LIFECYCLE.md의 전체 경로를 사용하세요. 사소하고 되돌리기 쉬운 수정만 Quick Fix로 분류하세요.

코드를 작성하기 전에 process/plans/active/ 아래에 PLAN_TEMPLATE.md를 복사해 다음을 포함한 실행 계획을 작성하세요.
- 목표와 범위
- 영향받는 파일 또는 구성요소
- 단계별 구현 작업
- 위험과 되돌리기 방법
- 실행할 검증 명령과 연결되는 acceptance criteria

docs/06_READINESS_GATE.md의 V1~V7 검증 계약을 채우세요. PASS 또는 승인된 CONDITIONAL이면 구현과 검증을 수행하세요. 완료 후 계획 폴더에 실제 변경, 증거, 남은 위험을 기록하고 process/plans/completed/로 옮기세요. 재사용 가능한 학습은 process/context/에 반영하세요. 프로젝트 사실을 AGENTS.md나 CLAUDE.md에 중복 기록하지 마세요.
```

## 기본 저장소 구조

```text
.
├── .github/
│   └── pull_request_template.md
├── apps/
│   ├── frontend/
│   │   ├── public/
│   │   ├── src/
│   │   └── tests/
│   └── backend/
│       ├── src/
│       └── tests/
├── packages/
│   ├── contracts/
│   │   ├── openapi/
│   │   └── schemas/
│   └── shared/
│       └── src/
├── database/
│   ├── migrations/
│   └── seeds/
├── infra/
│   ├── deployment/
│   └── docker/
├── process/
│   ├── context/                 # 현재 코드베이스 지식과 라우터
│   ├── development-protocols/   # 작업 라이프사이클
│   ├── plans/
│   │   ├── active/
│   │   │   ├── PLAN_TEMPLATE.md
│   │   │   ├── WORKLOG_TEMPLATE.md
│   │   │   └── HANDOFF_TEMPLATE.md
│   │   ├── backlog/
│   │   └── completed/
│   ├── features/                # 큰 기능별 장기 작업 묶음
│   └── evidence/                # 테스트·리뷰·수동 검증 증거와 릴리스 체크
├── docs/
│   ├── 00_PROJECT_BRIEF.md
│   ├── 01_REQUIREMENTS.md
│   ├── 02_ARCHITECTURE.md
│   ├── 03_ACCEPTANCE_CRITERIA.md
│   ├── 04_CONVENTIONS.md
│   ├── 05_INTERFACE_SPEC.md
│   ├── 06_READINESS_GATE.md
│   ├── decisions/
│   │   ├── README.md
│   │   └── ADR-000-template.md
│   └── plans/
│       ├── ACTIVE.md            # process/plans/active 라우터
│       └── COMPLETED.md         # process/plans/completed 라우터
├── skills/                      # 프로젝트 전용 반복 작업 레시피
├── tools/                       # 프로젝트 전용 개발·운영 도구
├── scripts/                     # 반복 가능한 개발·운영 작업
├── src/                         # 단일 서비스 프로필에서만 사용
├── tests/
│   ├── contract/
│   ├── e2e/
│   └── integration/
├── .env.example
├── .gitignore
├── AGENTS.md
├── CLAUDE.md
├── START_HERE.md                # 새 프로젝트 질문 인터뷰 진입점
└── README.md
```

## 완료의 의미

작업은 코드가 작성됐을 때가 아니라 다음 조건을 모두 만족할 때 완료됩니다.

- 연결된 요구사항과 acceptance criteria가 충족됐다.
- 화면·API·데이터·권한 계약이 구현과 일치한다.
- `docs/04_CONVENTIONS.md`에 정의된 필수 검증이 통과했다.
- 문서와 예제가 실제 동작과 일치한다.
- 계획이 `process/plans/completed/`로 이동했고 재사용 가능한 학습이 `process/context/`에 반영됐다.
- 비밀정보, 불필요한 생성물, 디버그 코드가 포함되지 않았다.
- 남은 위험과 후속 작업이 기록됐다.

## GitHub Template Repository로 사용하기

저장소를 GitHub에 올린 뒤 **Settings → General → Template repository**를 활성화하세요. 새 프로젝트를 만든 직후 이 README의 질문과 `docs/`의 `[답변]` 영역을 채우고, 템플릿 안내 문구는 프로젝트 설명으로 교체합니다.

## 구조 선택 원칙

- 웹앱 또는 풀스택 제품: `apps/frontend`, `apps/backend`, `packages`, `database`, `infra`를 사용합니다.
- API 전용 제품: `apps/backend`와 필요한 공통 패키지만 사용하고 프론트엔드 폴더는 삭제하거나 `해당 없음`으로 표시합니다.
- 단일 CLI·작은 자동화: 루트 `src/`와 `tests/`를 사용하고 `apps/`는 제거할 수 있습니다.
- 폴더를 남겨둔 채 사용하지 않는 경우 각 README에 `해당 없음`과 이유를 기록합니다.

## 프로젝트 라이프사이클

- **Research**: 기존 코드·문서·제약을 읽고 사실과 미정을 분리합니다.
- **Spec**: 사용자 결과, 범위, acceptance criteria를 승인 가능한 언어로 고정합니다.
- **Options**: 2~3개 접근 방식과 trade-off를 비교하고 결정을 기록합니다.
- **Plan**: 영향 파일, 계약, 단계, 위험, 롤백, 검증 증거를 정합니다.
- **Validate**: V1~V7 체크포인트로 실행 가능한 계약인지 판정합니다.
- **Execute**: 승인된 계획 범위에서 구현하고 계획 이탈을 기록합니다.
- **Closeout**: 검증을 다시 실행하고 계획을 보관하며 컨텍스트를 갱신합니다.
