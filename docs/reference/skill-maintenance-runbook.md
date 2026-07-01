# 스킬 유지보수 런북

## 목적

- `tighten-docs` 스킬 계약을 바꾼 뒤 검증, 설치본 동기화, 커밋, 푸시까지 닫는 절차를 소유한다.
- 이 문서는 배포 절차만 다루며, 스킬 방향은 `docs/skill-direction.md`, 배포 스킬 본문은 `skills/tighten-docs/SKILL.md`가 소유한다.

## 적용 범위

- `skills/tighten-docs/SKILL.md` 또는 `SKILL.ko.md`를 바꾼 경우.
- 스킬 방향 문서나 task 문서를 함께 정리한 경우.
- 로컬 설치본이 repo 변경을 따라가야 하는 경우.

## 절차

1. 변경 범위를 확인한다.

```bash
git status --short --untracked-files=all
git diff --stat
```

2. 스킬 본문을 검증한다.

```bash
python3 $CODEX_HOME/skills/.system/skill-creator/scripts/quick_validate.py skills/tighten-docs
```

`PyYAML`이 없는 Python이면 임시 venv에 `PyYAML`을 설치하고 같은 스크립트를 다시 실행한다. 이 경우 repo에는 의존성 파일을 추가하지 않는다.

3. project-context task 문서가 있으면 shape을 확인한다.

```bash
python3 <project-context-skill>/scripts/check_runtime_shape.py --repo-root .
```

4. whitespace 오류를 확인한다.

```bash
git diff --check
```

5. 로컬 설치본을 갱신한다.

```bash
npx skills add . -g -s tighten-docs -y --copy
```

Codex 설치본이 repo와 같은지 확인한다.

```bash
diff -u skills/tighten-docs/SKILL.md <global-skills-dir>/tighten-docs/SKILL.md
diff -u skills/tighten-docs/SKILL.ko.md <global-skills-dir>/tighten-docs/SKILL.ko.md
```

6. 커밋 전에 한 번 더 검증 결과와 diff 범위를 확인한다.

```bash
git status --short --untracked-files=all
git diff --stat
```

7. 커밋하고 푸시한다.

```bash
git add <intended-files>
git commit -m "<short change summary>"
git push
```

## 주의

- 설치본 동기화와 repo 변경은 별개다. 스킬 파일을 고쳤으면 설치본 diff 확인까지 닫는다.
- `README.md`는 사용자 설치/사용 진입점이고, 배포 절차를 반복 설명하지 않는다.
- `SKILL.md` 안에는 유지보수 절차를 넣지 않는다. 배포 스킬 본문은 실행 계약만 소유한다.
