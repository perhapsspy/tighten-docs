# Decisions


**2026-07-01**
- Background: 사용자는 `Conalog/patch-service`의 `.agents/skills` 전체를 현재 `tighten-docs` 보강 방향과 비교해 리뷰하라고 요청했다.
- Decision: 이번 작업은 새 task `docs/tasks/2026/07-01/patch-service-skills-review/`에서 원격 소스 감사로 관리한다.
- Why: 기존 `target-purpose-discipline` task는 실제 스킬 보강을 닫는 작업이고, 이번 요청은 외부 스킬 패턴 리뷰와 참고점 정리라는 별도 산출물을 가진다.
- Impact: 이 task는 `REVIEW.md`와 로그를 소유하며, `tighten-docs` 본문 수정은 후속 명시 요청 전까지 하지 않는다.
