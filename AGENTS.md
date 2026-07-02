# AGENTS.md

- 이 레포는 `tighten-docs` 스킬 리포다.
- 장기/재개 가능한 작업 맥락은 `$project-context` 기준으로 남긴다.
- 배포 스킬 계약은 `skills/tighten-docs/SKILL.md`에 둔다.
- `SKILL.md` 안에서 다른 스킬을 직접 참조하지 않는다.
- `SKILL.md`는 영어 기본 문서, `SKILL.ko.md`는 frontmatter 없는 한국어 페어로 유지한다.
- 명시적으로 영어가 필요한 파일을 제외하면 한글을 기본으로 쓴다.

## 역할 경계

- README는 소개, 설치, 사용 진입점, 기본 지원/라이선스 안내를 맡는다.
- `docs/skill-direction.md`는 방향과 진화 기준을 맡는다.
- `docs/reference/skill-maintenance-runbook.md`는 검증, 설치본 동기화, 커밋/푸시 절차를 맡는다.
- `skills/tighten-docs/`는 배포되는 스킬 본문을 맡는다.
