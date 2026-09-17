# Claude Code Router

이 파일은 Claude Code 전용 진입점입니다. 프로젝트 지식은 여기에 저장하지 않습니다. 공통 작업 규칙은 `AGENTS.md`, 프로젝트 사실은 `docs/`를 Source of Truth로 사용합니다.

## 프로젝트 시작 전 사용자가 답해야 할 질문

- Claude Code가 세션 시작 시 항상 읽어야 할 추가 문서가 있는가? `[답변: 없다면 "없음"]`
- Claude Code가 실행 전에 반드시 확인받아야 할 명령 또는 경로는 무엇인가? `[답변]`
- 프로젝트에 Claude Code 전용 도구, MCP 서버, hook 또는 skill이 있는가? `[답변: 이름과 사용 조건만 기록]`
- 긴 작업에서 진행 상황을 기록할 위치는 어디인가? `[기본값: docs/plans/ACTIVE.md]`
- 공통 지침과 다른 Claude Code 전용 예외가 정말 필요한가? `[답변: 없다면 "없음"; 있다면 이유와 만료 조건 기록]`

## 세션 시작 절차

1. 루트의 `AGENTS.md`를 읽고 공통 작업 규칙을 따릅니다.
2. `AGENTS.md`에 정의된 순서대로 요청과 관련된 `docs/`를 읽습니다.
3. 현재 변경 상태와 관련 코드를 확인합니다.
4. `process/development-protocols/LIFECYCLE.md`에서 Quick Fix 또는 전체 경로를 선택합니다.
5. 비단순 작업이면 구현 전에 `process/plans/active/`에 계획을 만듭니다.
6. `docs/06_READINESS_GATE.md`로 검증 계약을 확정하고 구현 후 동일 항목을 다시 확인합니다.
7. 완료된 계획은 `process/plans/completed/`로 옮기고 `process/context/`를 갱신합니다.

## Claude Code 전용 규칙

- 이 파일과 `AGENTS.md`가 겹치면 `AGENTS.md`의 공통 규칙을 우선합니다.
- 요구사항, 명령어, 기술 스택을 이 파일에 복사하지 말고 해당 `docs/` 문서를 수정합니다.
- 계획 모드는 계획 수립과 검토에 사용하고, 승인된 범위에서는 구현·테스트·문서화까지 완료합니다.
- 도구 권한이 없거나 명령이 실패하면 우회해 성공한 것처럼 처리하지 말고 차단 원인과 재현 명령을 기록합니다.
- 대규모 작업은 독립적으로 검증 가능한 단계로 나누고, 각 단계의 상태를 `docs/plans/ACTIVE.md`에 반영합니다.

## 선택적 프로젝트별 확장

Claude Code에만 필요한 지침이 있을 때만 아래에 추가하세요. 프로젝트 일반 지식은 추가하지 않습니다.

```text
[답변: Claude Code 전용 도구/권한/세션 규칙. 없으면 이 블록 삭제]
```
