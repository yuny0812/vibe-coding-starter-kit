# Shared Contracts

프론트엔드, 백엔드, 외부 소비자가 공유하는 기계 판독 가능한 계약의 Source of Truth입니다.

## 프로젝트 시작 전 사용자가 답해야 할 질문

- OpenAPI, JSON Schema, GraphQL schema, protobuf 중 무엇을 사용하는가? `[답변]`
- 계약 우선(contract-first)인가 코드 우선(code-first)인가? `[답변]`
- 타입 또는 클라이언트 코드를 어떻게 생성하는가? `[답변]`
- breaking change와 버전 관리는 어떻게 하는가? `[답변]`
- 계약 호환성 검사는 어떤 명령으로 실행하는가? `[답변]`

## 디렉터리

- `openapi/`: REST API 계약
- `schemas/`: JSON Schema, 이벤트, 공유 데이터 계약

생성된 코드는 `[생성 위치]`에 두고 수동 수정하지 않습니다.
