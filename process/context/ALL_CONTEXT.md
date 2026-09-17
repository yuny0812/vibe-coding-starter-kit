# Context Router

- 최종 수정일: `YYYY-MM-DD`
- 코드 기준 revision: `[commit SHA/branch 또는 초기 템플릿]`

이 파일은 전체 지식을 담는 백과사전이 아니라, 작업에 필요한 가장 작은 컨텍스트로 연결하는 라우터입니다. 내용은 추정이 아니라 실제 코드와 설정에서 확인한 사실로 갱신합니다.

## 프로젝트 시작 전 사용자가 답해야 할 질문

- 현재 구현된 앱·서비스는 무엇인가? `[답변]`
- 실제 기술 스택과 버전은 무엇인가? `[답변]`
- 설치, 실행, 테스트의 canonical command는 무엇인가? `[답변]`
- 가장 자주 작업하는 코드 영역은 어디인가? `[답변]`
- 에이전트가 매번 알아야 하지만 `docs/`에 없는 구현 사실은 무엇인가? `[답변]`

## Quick Context

- 제품 목표: `../../docs/00_PROJECT_BRIEF.md`
- 요구사항: `../../docs/01_REQUIREMENTS.md`
- 아키텍처: `../../docs/02_ARCHITECTURE.md`
- 완료 기준: `../../docs/03_ACCEPTANCE_CRITERIA.md`
- 명령·규칙: `../../docs/04_CONVENTIONS.md`
- 화면·API 계약: `../../docs/05_INTERFACE_SPEC.md`
- 기술 결정: `../../docs/decisions/`
- 활성 계획: `../plans/active/`

## Implementation Map

| 영역 | 코드 경로 | 책임 | 주요 진입점 | 테스트 위치 | 추가로 읽을 문서 |
|---|---|---|---|---|---|
| Frontend | `../../apps/frontend/` | `[책임]` | `[경로]` | `[경로]` | `[문서]` |
| Backend | `../../apps/backend/` | `[책임]` | `[경로]` | `[경로]` | `[문서]` |
| Contracts | `../../packages/contracts/` | `[책임]` | `[경로]` | `[경로]` | `[문서]` |
| Database | `../../database/` | `[책임]` | `[경로]` | `[경로]` | `[문서]` |
| Infrastructure | `../../infra/` | `[책임]` | `[경로]` | `[경로]` | `[문서]` |

## Commands

| 목적 | 명령 | 실행 위치 | 비고 |
|---|---|---|---|
| Install | `[명령]` | `[경로]` | `[비고]` |
| Run | `[명령]` | `[경로]` | `[비고]` |
| Verify | `[명령]` | `[경로]` | `[비고]` |

## Update Triggers

다음이 바뀌면 이 라우터와 관련 컨텍스트를 갱신합니다.

- 앱, 패키지, 주요 폴더 경계
- runtime·framework·database·auth
- canonical command 또는 CI gate
- 주요 진입점, route, schema, 외부 연동
- 여러 작업에서 반복해 필요한 구현 패턴
