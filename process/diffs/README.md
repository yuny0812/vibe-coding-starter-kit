# Change Records (Diffs)

이 폴더는 코드·설정·문서를 의도적으로 바꾼 이유와 결과를 사람이 읽을 수 있게 기록합니다. 실제 줄 단위 diff와 정확한 변경 이력의 Source of Truth는 Git commit과 pull request입니다. 이곳에는 패치 전체를 복사하지 않고, Git만으로 알기 어려운 맥락·전후 동작·검증·롤백을 남깁니다.

## 언제 작성하는가

- 코드 또는 설정의 동작을 바꾼 모든 변경
- 여러 파일에 걸친 문서 구조나 개발 프로세스 변경
- 사용자가 직접 수정했지만 나중에 이유와 영향을 추적해야 하는 변경
- 계획과 다르게 구현했거나 후속 작업·잔여 위험이 있는 변경

오탈자처럼 동작과 의사결정에 영향이 없는 수정은 Git commit message만으로 충분합니다. 하나의 목적을 가진 여러 commit은 하나의 change record로 묶을 수 있습니다.

## 파일 규칙

- 파일명: `YYYY-MM-DD-<topic>.md`
- `DIFF_TEMPLATE.md`를 복사해 작성합니다.
- 작성 시점에는 상태를 `in-progress`, 병합·배포 또는 작업 종료 후에는 `completed`로 바꿉니다.
- commit SHA 또는 PR 링크를 반드시 추가해 실제 diff로 이동할 수 있게 합니다.
- 관련 리서치, 요구사항, ADR, 계획과 상호 링크합니다.
- 전체 patch, 생성 파일, 비밀값, 개인정보는 이 폴더에 복사하지 않습니다.

## Git diff와의 관계

- 무엇이 정확히 바뀌었는가: Git commit 또는 PR diff
- 왜 바꿨고 어떤 동작이 달라졌는가: 이 폴더의 change record
- 무엇을 조사했는가: `process/research/`
- 무엇을 검증했는가: 이 문서의 Verification과 `process/evidence/`
- 현재의 지속 사실은 무엇인가: `docs/`와 `process/context/`

## Index

| 날짜 | 변경 | 상태 | commit / PR | 관련 research |
|---|---|---|---|---|
| YYYY-MM-DD | 예: 로그인 오류 처리 변경 | in-progress | 링크 | 링크 또는 N/A |
