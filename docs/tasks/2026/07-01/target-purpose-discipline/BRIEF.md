# Tighten Docs 목적 중심 교정 보강

## Goal

- `tighten-docs`가 선택된 문서나 diff를 고칠 때, 문장의 길이만 줄이는 수준을 넘어 대상 문서의 단일 목적과 핵심 주체를 먼저 잡도록 스킬 계약을 보강한다.

## Scope

- 배포 스킬 계약과 한국어 페어를 실제 리포에서 수정한다.
- 이번 작업의 중심은 문서 교정 기준이며, 새 문서 생성 스킬이나 문서 구조 설계 스킬로 범위를 넓히지 않는다.

## Current Understanding

- 최근 지적의 핵심은 “짧게 고치기” 자체가 아니라, 대상 문서가 맡은 목적과 독자 행동을 흐리는 agent 편의성, 작업 기록, 방어 문구, 구현 인접 서술을 걷어내는 것이다.
- 교정 전에 대상의 단일 역할, 핵심 주체, 독자 행동, 문서가 책임지는 약속을 잡아야 한다.
- 최신 지적은 기존 문장에 붙는 주석이 아니라 대상 전체를 다시 읽는 기준이다.
- 거절되거나 더 이상 현재 목적에 속하지 않는 내용은 경고, 사유, 제외 목록, 반례로 보존하지 않는 방향이 유지되어야 한다.
- 기능 목록, 코드 구조, 발견 순서, 쓰기 쉬운 서술 순서가 독자에게 필요한 구조를 밀어내는 것도 직접 다뤄야 한다.

## Current State

- 목적 중심 교정 계약은 배포 스킬 본문, 한국어 페어, 방향 문서에 반영됐다.
- 검증은 repo/설치본 `quick_validate`, project-context shape check, `git diff --check`까지 통과했다.
- 설치본은 `npx skills add . -g -s tighten-docs -y --copy`로 갱신됐고, Codex 설치 경로는 리포 스킬 파일과 일치한다.
- 반복되는 유지보수 closeout 절차는 `docs/reference/skill-maintenance-runbook.md`가 소유한다.

## Next Step

- Reopen if 새 피드백이 목적 중심 계약을 더 줄이거나 다른 설치/배포 흐름으로 닫으라고 요구할 때.

## Working Boundary

- `skills/tighten-docs/SKILL.md`
- `skills/tighten-docs/SKILL.ko.md`
- `docs/skill-direction.md`
- `docs/tasks/2026/07-01/target-purpose-discipline/`
