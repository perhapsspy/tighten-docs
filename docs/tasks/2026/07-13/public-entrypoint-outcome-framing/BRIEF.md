# 공개 진입점 결과 중심 문구

## Goal

- 공개 README, 목록 설명과 onboarding이 내부 제작 절차보다 독자가 확인할 수 있는 상황·결과·다음 행동을 먼저 말하게 한다.

## Scope

- `tighten-docs` runtime 계약과 한국어 페어에 최소 규칙을 추가한다.
- 공개 소개, 절차 중심 문서, 근거 없는 편익과 공개·기술 혼합 문서를 forward-test한다.
- 설치본 동기화와 release는 검증 뒤 별도 범위로 둔다.

## Current Understanding

- 기존 계약은 대상 역할, 독자 행동과 소유 약속을 이미 요구하지만 공개 진입점의 평가·선택·사용 시작을 명시하지 않는다.
- 결과 중심 문구는 확인된 사실만 사용해야 하며 runbook, API contract와 ADR의 절차 목적을 마케팅 문구로 바꾸면 안 된다.

## Current State

- 영문 runtime과 한국어 페어, skill direction에 공개 진입점용 최소 규칙을 반영했다.
- 공개 README·목록·runbook, 영어 SDK README·webhook 계약, 실제 저장소 README까지 세 라운드 dogfood를 마쳤다.
- 공개 진입점은 결과와 다음 행동을 앞세웠고 기술·운영 문서는 절차 계약과 미결정 경계를 보존했다.
- skill validator, task log 검사와 diff whitespace 검사를 통과했다. 전체 project-context 검사는 이번 diff 밖 유지보수 런북의 기존 환경별 경로 표기에서 실패한다.

## Next Step

- 사용자가 허용하면 로컬 설치본 동기화와 release를 별도 작업으로 진행한다.

## Working Boundary

- `skills/tighten-docs/`
- `docs/skill-direction.md`
- `docs/tasks/2026/07-13/public-entrypoint-outcome-framing/`
