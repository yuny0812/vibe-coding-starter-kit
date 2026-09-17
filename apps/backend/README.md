# Backend Application

API, 도메인 규칙, 비동기 작업, 외부 시스템 연동과 서버 측 보안을 소유합니다. 공개 계약은 `packages/contracts/`, 동작 명세는 `docs/05_INTERFACE_SPEC.md`를 따릅니다.

## 프로젝트 시작 전 사용자가 답해야 할 질문

- 어떤 언어·프레임워크·런타임 버전을 사용할 것인가? `[답변]`
- API 형태와 버전 정책은 무엇인가? `[REST/GraphQL/RPC/Event 등]`
- 인증, 권한, 세션을 어디서 처리하는가? `[답변]`
- 동기 요청과 비동기 작업의 경계는 무엇인가? `[답변]`
- 데이터 접근, transaction, migration 정책은 무엇인가? `[답변]`
- 로그, 지표, 추적, 오류 보고 도구는 무엇인가? `[답변]`
- 백엔드 테스트의 범위와 실행 명령은 무엇인가? `[답변]`

## 기본 경계

- `src/`: API, application, domain, infrastructure 코드
- `tests/`: 백엔드 단위·통합 테스트
- UI 컴포넌트와 클라이언트 전용 상태를 이 앱에 두지 않습니다.
- 외부에 노출되는 schema를 코드에만 숨기지 말고 `packages/contracts/`와 동기화합니다.
