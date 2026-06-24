# Decisions

**2026-06-24**

- Background: 기존 세 개 스킬은 문서 구조, 작업 맥락, 기준 소스 감사처럼 관심사가 다르고, 사용자는 한국어 사례를 공개 스킬로 일반화할 필요를 지적했다.
- Decision: 새 스킬은 이미 선택된 문서나 diff의 교정 편집에만 집중하고, 언어 규칙은 required language and locale 보존으로 둔다.
- Why: 관찰된 실패의 핵심은 새 구조 설계가 아니라 최신 지적을 실제 본문에 반영하지 못하고 방어적 설명이나 불필요한 비사용 언어를 늘리는 데 있다.
- Impact: 배포 스킬 본문은 source-of-truth, task-state, documentation architecture를 범위 밖으로 두고, 모든 언어권에 적용되는 표현을 사용한다.

**2026-06-24**
- Background: 스킬 리포로서 기본 루트 파일을 더 갖춰야 하는지 재검토했고, 현재 리포에는 별도 빌드나 릴리스 자동화가 없다.
- Decision: 기본 리포 위생은 .gitignore, .gitattributes, .editorconfig로 제한하고, CI workflow, package manifest, CONTRIBUTING류 문서는 실제 운영 절차가 생길 때 추가한다.
- Why: 지금 없는 자동화나 기여 절차를 문서로 먼저 만들면 스킬 본문처럼 짧고 독립적인 리포라는 방향과 충돌하고 유지보수 표면만 늘어난다.
- Impact: 루트 파일은 검증 산출물과 편집기 차이를 막는 최소 장치만 제공하며, 후속 세션은 새 도구가 생기기 전까지 패키지/CI 문서를 만들지 않는다.

**2026-06-24**
- Background: docs/reference/skill-repository.md가 AGENTS, README, 배포 스킬 본문과 겹치고, 일부 내용은 다른 스킬이나 저장소 운영 지침이 감당할 성격이었다.
- Decision: 별도 저장소 참조 문서를 삭제하고, 현재 리포에는 README, AGENTS, docs/skill-direction.md, task logs만 남긴다.
- Why: 이 스킬은 문서 교정용이며, 리포 내부 운영 규칙이나 관련 스킬 라우팅을 별도 참조 문서로 키울수록 스킬 자체의 목적과 충돌한다.
- Impact: 후속 작업은 저장소 운영 규칙은 AGENTS에, 사용자 진입 설명은 README에, 스킬 진화 기준은 docs/skill-direction.md에만 둔다.

**2026-06-24**
- Background: 사용자가 기존 이름이 너무 길고 둔하다고 지적했고, 초기 커밋 전이라 스킬/리포 이름을 바꿀 수 있는 상태였다.
- Decision: 스킬명과 리포명을 tighten-docs로 줄인다.
- Why: tighten-docs는 동사형 호출이 자연스럽고, 교정 편집 대상이 문서라는 점을 유지하면서 tighten-doc-revisions보다 짧다.
- Impact: 스킬 폴더, frontmatter name, README 설치/호출 예시, AGENTS, task slug, origin URL, 로컬 리포 디렉터리를 tighten-docs 기준으로 맞춘다.
