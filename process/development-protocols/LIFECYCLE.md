# Development Lifecycle Protocol

## 프로젝트 시작 전 사용자가 답해야 할 질문

- 단계별 사용자 승인이 필요한가, 한 번 승인 후 자율 진행하는가? `[답변]`
- 어떤 변경은 무조건 전체 경로를 사용해야 하는가? `[기본값: 인증, 권한, API, DB schema, 결제, migration, 인프라]`
- Validate의 CONDITIONAL 판정 권한자는 누구인가? `[답변]`
- 계획 이탈 시 중단 기준은 무엇인가? `[답변]`

## Full Path

Project Lifecycle Kit의 네 구간과 이 저장소의 일곱 단계를 다음처럼 연결합니다.

| Kit 구간 | 이 저장소의 단계 | 핵심 산출물 |
|---|---|---|
| 기획 | Research → Spec → Options → Plan → Validate | 승인 가능한 계획과 준비도 판정 |
| 구축 | Execute | 작은 작업 단위, worklog, 테스트 결과 |
| 검증 | Validate 재확인 → Closeout | 요구사항 커버리지와 release evidence |
| 운영 | Closeout 이후 | 배포·관측·롤백·인계 기록 |

1. **Research** — 코드와 문서를 읽고 확인된 사실, 모순, 미정 사항, 영향 범위를 기록합니다. 제품 코드는 수정하지 않습니다.
2. **Spec** — 사용자 스토리, 포함·제외 범위, 요구사항, acceptance criteria를 평이한 언어로 고정합니다.
3. **Options** — 현실적인 접근 2~3개, trade-off, 선택·기각 이유를 기록합니다. 장기 영향은 ADR로 남깁니다.
4. **Plan** — 수정 예상 파일, 공개 계약, 단계, migration, 위험, 롤백, 검증 증거를 정의합니다.
5. **Validate** — `docs/06_READINESS_GATE.md`의 V1~V7을 `PASS`, `CONDITIONAL`, `BLOCKED`로 판정합니다.
6. **Execute** — 승인된 계획 범위에서 구현합니다. 계획과 달라지면 이유와 영향을 계획에 기록합니다.
7. **Closeout** — 검증을 독립적으로 다시 실행하고 evidence를 저장한 뒤 계획을 completed로 옮기고 context를 갱신합니다.

구축 중에는 한 번에 하나의 작업만 진행하고, 각 작업에 요구사항 ID·영향 파일·완료 판정을 연결합니다. 계획과 다르게 구현한 내용은 `WORKLOG.md`에 남기고 관련 명세도 함께 갱신합니다.

## Quick Fix Path

다음을 모두 만족할 때만 사용합니다.

- 작은 단일 목적의 변경이다.
- 공개 계약, DB schema, 인증·권한, 결제, migration, 인프라를 바꾸지 않는다.
- 쉽게 되돌릴 수 있다.
- 영향 파일과 필요한 검증을 바로 특정할 수 있다.

흐름:

```text
Inspect → Edit → Scoped Verify → Report
```

## Hard Stops

- 사용자 요청과 승인된 요구사항이 충돌한다.
- 비밀값 또는 민감정보 노출 가능성이 있다.
- 데이터 손실이나 되돌릴 수 없는 migration 위험이 해결되지 않았다.
- 완료를 증명할 검증 방법이 없다.
- 계획 이탈이 사용자 결과 또는 승인 범위를 바꾼다.
