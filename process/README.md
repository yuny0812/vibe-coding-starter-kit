# Project Lifecycle

`process/`는 작업이 시작되어 완료될 때까지의 실행 기록입니다. 승인된 제품 지식은 `docs/`, 현재 코드베이스의 사실은 `context/`, 조사 근거는 `research/`, 일시적인 작업 상태는 `plans/`, 변경 맥락은 `diffs/`에 둡니다.

재사용 가능한 방법론·게이트 자체는 별도 Project Lifecycle Kit의 책임입니다. 이 폴더에는 해당 프로젝트에서 실제로 작성된 리서치, 계획, 작업 로그, 변경 기록, 인계, 검증 증거만 둡니다.

## 프로젝트 시작 전 사용자가 답해야 할 질문

- 큰 기능에서 사람 검토가 필요한 단계는 어디인가? `[답변]`
- Quick Fix로 처리할 수 있는 최대 범위는 무엇인가? `[답변]`
- 동시에 진행할 수 있는 활성 계획 수는 몇 개인가? `[기본값: 1개]`
- 완료 증거를 얼마나 오래 보관하는가? `[답변]`
- 기능별 폴더로 승격할 기준은 무엇인가? `[기본값: 3단계 이상 또는 산출물 5개 이상]`

## 디렉터리 역할

- `context/`: 실제 코드베이스에서 확인한 지속 지식과 라우터
- `research/`: 조사 질문, 출처, 실험, 대안과 결론
- `development-protocols/`: Research부터 Closeout까지 작업 규칙
- `plans/active/`: 현재 작업 폴더와 계획
- `plans/backlog/`: 범위가 정의됐지만 아직 시작하지 않은 계획
- `plans/completed/`: 완료된 계획, 결과, 잔여 위험
- `features/`: 여러 계획과 산출물을 갖는 큰 기능 영역
- `diffs/`: 변경 전후, 이유, 관련 Git diff, 검증과 롤백을 연결하는 change record
- `evidence/`: 테스트, 리뷰, 스크린샷, 벤치마크 등 완료 증거

## 기록 연결 원칙

- 조사에서 구현으로 이어질 때 research → plan → diff → commit 또는 PR 순서로 상호 링크합니다.
- 실제 줄 단위 변경은 Git이 원본이며, `diffs/`에는 patch 전체가 아니라 사람이 이해해야 할 맥락을 기록합니다.
- 리서치나 변경 결과가 지속 사실이 되면 관련 `docs/`, ADR 또는 `context/`를 갱신합니다.
- 작은 Quick Fix도 동작이나 의사결정에 영향을 주면 `diffs/`에 남깁니다.

활성 계획 폴더의 권장 구성:

```text
process/plans/active/<feature>/
├── PLAN.md       # PLAN_TEMPLATE.md에서 복사
├── WORKLOG.md    # 판단·가정·계획 이탈 기록
└── HANDOFF.md    # 세션이 바뀔 때만 사용
```

## Lifecycle

```text
Research → Spec → Options → Plan → Validate → Execute → Closeout
```

- Research 결과는 필요할 때 `research/`에 저장합니다.
- Execute와 Closeout에서는 의미 있는 변경을 `diffs/`에 연결하고 commit 또는 PR 링크를 추가합니다.
- 상세 규칙은 `development-protocols/LIFECYCLE.md`를 따릅니다.
