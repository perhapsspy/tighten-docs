# Patch-Service 문서 스킬 리뷰

## Goal

- `Conalog/patch-service`의 `.agents/skills` 전체를 현재 `main` 기준으로 리뷰하고, `tighten-docs`의 목적 중심 교정 계약과 유사하거나 참고할 문서 스킬 패턴을 정리한다.

## Scope

- 원격 소스 기준은 `Conalog/patch-service` `main`의 `.agents/skills`다.
- 결과는 이 task의 현재 리뷰 문서와 로그에 남긴다.
- 이번 작업은 참고 감사이며, `tighten-docs` 스킬 본문을 바로 수정하지 않는다.

## Current Understanding

- 원격 `main` 커밋은 `30f6b606c395e4f41e295437699a1b213ed4dda6`이다.
- 확인 대상 스킬은 7개다: `context-driven-development`, `coupling-analysis`, `documentation-and-adrs`, `domain-analysis`, `hads`, `modular-decomposition`, `modular-design-principles`.
- 리뷰 초점은 문서 목적, 주체, 독자 행동, 소유 약속, agent 편의/과정 보존을 어떻게 다루는지다.

## Current State

- `REVIEW.md`는 7개 스킬 전체의 역할, 유사점, 참고점, 비채택 경계를 통합한 상태다.
- 현재 권고는 `tighten-docs` 본문을 추가 수정하지 않고, 참고 가능한 판단 언어와 도입 금지 경계만 리뷰 문서에 남기는 것이다.
- 검증은 project-context shape check와 `git diff --check`까지 통과했다.

## Next Step

- Reopen if 새 피드백이 `REVIEW.md` 결론을 더 줄이거나 `tighten-docs` 본문 반영까지 진행하라고 요구할 때.

## Working Boundary

- `docs/tasks/2026/07-01/patch-service-skills-review/`
- 원격 소스: `.agents/skills/**`
