# Change Record: Research and Diff Tracking

- Date: 2026-09-18
- Status: completed
- Owner: yuny0812 with Codex
- Pull request: N/A — committed directly to `main`
- Related requirement: 사용자 요청 — 리서치 보관 공간과 임의 코드 변경 추적 체계 추가
- Related research: N/A
- Related plan or ADR: N/A — 문서 구조 변경

## Commits

- [4e678d1](https://github.com/yuny0812/vibe-coding-starter-kit/commit/4e678d1f77baf5f171e2548c2414e3dd047ba903) — research workspace guide
- [dab717d](https://github.com/yuny0812/vibe-coding-starter-kit/commit/dab717d91bb128dac8aa745324f82176d3176edf) — research template
- [c4a986e](https://github.com/yuny0812/vibe-coding-starter-kit/commit/c4a986e17186fddde08bc893358fdedbdf7c28f3) — diff tracking guide
- [5b49aad](https://github.com/yuny0812/vibe-coding-starter-kit/commit/5b49aadcc240739af4b99f7a15f606b7f3c496a3) — change record template
- [e07b7cd](https://github.com/yuny0812/vibe-coding-starter-kit/commit/e07b7cdb3d7096615a55dc73c850cfbb684f4bc1) — process overview integration
- [2ed665e](https://github.com/yuny0812/vibe-coding-starter-kit/commit/2ed665ed442633cdce3b241f095df30dba1683d9) — lifecycle integration
- [3ed1973](https://github.com/yuny0812/vibe-coding-starter-kit/commit/3ed19737ba4cc63df571f9e6a7373f844c773289) — root README integration
- [This record history](https://github.com/yuny0812/vibe-coding-starter-kit/commits/main/process/diffs/2026-09-18-research-and-diff-tracking.md)

## Why

저장소에 조사 자료를 독립적으로 보관할 위치와, 사용자가 직접 수정하거나 에이전트가 구현한 변경의 이유·영향·검증을 추적할 표준 문서가 없었습니다.

## Before

- Research 단계는 정의되어 있었지만 조사 산출물의 전용 위치와 템플릿이 없었습니다.
- Git은 줄 단위 변경을 추적했지만, 변경 이유와 전후 동작, 검증, 롤백을 연결하는 사람용 기록은 없었습니다.
- `process/`의 기존 구조는 context, plans, features, evidence 중심이었습니다.

## After

- `process/research/`에 조사 규칙, 색인, 복사용 템플릿을 추가했습니다.
- `process/diffs/`에 Git diff를 보완하는 change record 규칙, 색인, 복사용 템플릿을 추가했습니다.
- 루트 README, process 안내와 lifecycle이 새 산출물을 언제 만들고 어떻게 연결할지 설명합니다.
- 전체 patch는 복제하지 않고 commit/PR을 Source of Truth로 유지합니다.

## Files and contracts affected

| Path | Change | Reason |
|---|---|---|
| `process/research/README.md` | 보관·색인 규칙 추가 | 조사 근거를 일관되게 보존 |
| `process/research/RESEARCH_TEMPLATE.md` | 질문·출처·실험·결론 템플릿 추가 | 반복 가능한 작성 형식 제공 |
| `process/diffs/README.md` | Git diff와 change record 역할 정의 | 변경 맥락 추적 |
| `process/diffs/DIFF_TEMPLATE.md` | 전후 동작·검증·롤백 템플릿 추가 | 임의 수정도 같은 형식으로 기록 |
| `process/README.md` | 디렉터리 역할과 연결 원칙 갱신 | 새 폴더 발견성 확보 |
| `process/development-protocols/LIFECYCLE.md` | Research, Execute, Closeout 산출물 연결 | 실제 작업 흐름에 포함 |
| `README.md` | 시작 순서, Source of Truth, 구조 트리 갱신 | 템플릿 사용자에게 안내 |

## Decisions and deviations

- Decision: 정확한 줄 단위 diff는 Git에 두고, `process/diffs/`에는 Git만으로 알기 어려운 맥락만 기록합니다.
- Decision: 파일명은 날짜와 주제를 사용해 정렬과 검색을 쉽게 합니다.
- Plan deviation: N/A.

## Verification

| Check | Method | Result | Evidence |
|---|---|---|---|
| 새 폴더와 템플릿 존재 | GitHub `main` 파일 목록 확인 | pass | `process/research/`, `process/diffs/` |
| Markdown 렌더링 | GitHub Preview와 커밋 후 페이지 확인 | pass | 각 README 및 템플릿 페이지 |
| 기존 흐름 연결 | `process/README.md`, lifecycle, root README 확인 | pass | 위 commit 링크 |
| 코드 테스트 | 문서 전용 변경 | not run | 제품 코드 변경 없음 |

## Risk and rollback

- Remaining risk: 기록 품질은 작업자가 템플릿과 링크 규칙을 지키는 정도에 좌우됩니다.
- Rollback trigger: 기존 프로세스와 중복되거나 유지 비용이 가치보다 커질 때.
- Rollback steps: 위 커밋을 역순으로 revert하고 README 참조를 제거합니다.

## Follow-ups

- [ ] N/A
