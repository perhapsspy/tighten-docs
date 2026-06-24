# Tighten Docs 스킬 생성

## Goal

- 교정 편집 스킬을 perhapsspy 계열 로컬 스킬 리포로 만들고, 새 세션에서 바로 이어 검토할 수 있게 한다.

## Scope

- 스킬/리포 이름: `tighten-docs`
- 배포 스킬: `skills/tighten-docs/`
- 리포 운영 문서: README, AGENTS, 방향 문서

## Current Understanding

- 이 스킬은 새 문서 작성용이 아니라, 이미 선택된 문서나 diff를 최신 지적 기준으로 줄이고 고치는 교정 편집용이다.
- 핵심 문제는 거절된 내용을 경고로 되살리는 것, 방어적 설명을 늘리는 것, 사용자나 리포의 요구 언어를 지키지 않는 것이다.
- 공개 스킬로는 한국어 전용이 아니라 “요구 언어와 로캘 보존”으로 일반화한다.
- 확인되지 않은 레거시 호환, 대체 경로, 예외, 라우팅을 새로 만드는 것도 배포 스킬의 직접 방어 대상이다.
- 국소 교정을 사용자가 요구하지 않은 문서 간 정책으로 확대하는 것도 최신 지적 과적응의 직접 방어 대상이다.
- 이름은 `tighten-docs`로 확정됐다.

## Current State

- 로컬 git 리포가 초기화됐고, `origin`은 `https://github.com/perhapsspy/tighten-docs.git`로 설정됐다.
- 로컬 리포 디렉터리도 `tighten-docs` 이름으로 이동됐다.
- `main`은 GitHub origin에 push됐고, 스킬은 `$CODEX_HOME/skills/tighten-docs`에 설치됐다.
- 배포 스킬 본문과 한국어 페어, OpenAI 인터페이스 프롬프트, README가 위 방어선에 맞게 정리됐다.
- 스킬 기준을 리포 문서에 자기적용해 README의 예시와 사용 사례를 더 짧고 쉬운 문장으로 압축했다.
- `docs/reference/skill-repository.md`는 AGENTS/README/스킬 본문과 겹쳐 삭제했다.
- 루트에는 `.gitignore`, `.gitattributes`, `.editorconfig` 수준의 최소 리포 위생 파일만 추가됐다.
- `SKILL.md`는 관련 스킬을 직접 참조하지 않고 독립 실행 계약으로 유지된다.
- `skill-creator` quick validation, `project-context` shape 검사, worklog/decision log shape 검사를 다시 통과했다.
- 설치된 스킬 복사본도 `skill-creator` quick validation을 통과했다.
- 로컬 리포의 영어 기본 `SKILL.md`와 한국어 페어 `SKILL.ko.md`에는 국소 교정을 새 cross-document policy로 넓히지 말라는 규칙이 추가됐다.
- 이번 변경은 `$CODEX_HOME/skills/tighten-docs` 설치본에도 반영됐고, 리포와 설치본 파일 비교 및 설치본 `skill-creator` quick validation을 통과했다.
- 이번 변경 검증은 임시 venv의 PyYAML로 `skill-creator` quick validation 통과, `project-context` runtime shape 통과 상태다.

## Next Step

- Codex가 갱신된 설치본을 새로 읽어야 하면 Codex를 재시작한다.

## Working Boundary

- `skills/tighten-docs/SKILL.md`
- `skills/tighten-docs/SKILL.ko.md`
- `docs/skill-direction.md`
- `docs/tasks/2026/06-24/create-tighten-docs/`
