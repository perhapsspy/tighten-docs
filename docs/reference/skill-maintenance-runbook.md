# 스킬 유지보수 런북

## 목적

`tighten-docs`의 변경을 검증하고, 승인된 경우에만 설치본·원격 저장소까지 안전하게 반영하는 절차다. 스킬 방향은 `docs/skill-direction.md`, 실행 계약은 `skills/tighten-docs/SKILL.md`가 소유한다.

## 시작 전

- 저장소 루트에서 실행한다.
- 의도하지 않은 변경이 보이면 중단하고 범위를 확인한다.
- 푸시는 사용자가 이번 작업에서 명시적으로 허용한 경우에만 한다.

```bash
git status --short --untracked-files=all
git diff --stat
```

## 검증

1. 설치된 `skill-creator`의 검증 스크립트를 찾고 스킬을 검사한다.

```bash
home_dir="$(cd && pwd)"
skill_creator_root="${CODEX_HOME:-$home_dir/.codex}/skills/.system/skill-creator"
test -f "$skill_creator_root/scripts/quick_validate.py" || {
  echo "skill-creator validation script not found: $skill_creator_root" >&2
  exit 1
}
python3 "$skill_creator_root/scripts/quick_validate.py" skills/tighten-docs
```

`PyYAML`이 없다면 임시 가상환경에만 설치하고 같은 명령을 다시 실행한다. 저장소에 임시 의존성 파일을 추가하지 않는다.

2. `project-context` task가 있는 저장소라면 task 구조를 검사한다.

```bash
home_dir="$(cd && pwd)"
project_context_root="$home_dir/.agents/skills/project-context"
if test -d docs/tasks; then
  test -f "$project_context_root/scripts/check_runtime_shape.py" || {
    echo "project-context checker not found: $project_context_root" >&2
    exit 1
  }
  python3 "$project_context_root/scripts/check_runtime_shape.py" --repo-root .
fi
```

3. diff와 whitespace를 확인한다.

```bash
git diff --check
git status --short --untracked-files=all
git diff --stat
```

검증 실패, 예상 밖 파일 변경, 원격과 충돌 가능성이 있으면 여기서 중단한다.

## 로컬 설치본 갱신

로컬 설치 갱신이 작업 범위에 포함된 경우에만 실행한다.

```bash
npx skills add . -g -s tighten-docs -y --copy
home_dir="$(cd && pwd)"
installed_skill_root="$home_dir/.agents/skills/tighten-docs"
diff -u skills/tighten-docs/SKILL.md "$installed_skill_root/SKILL.md"
diff -u skills/tighten-docs/SKILL.ko.md "$installed_skill_root/SKILL.ko.md"
```

설치 명령이 실패하면 저장소 변경은 그대로 두고 오류를 보고한다. 기존 설치본을 임의로 삭제하지 않는다.

## 커밋과 푸시

1. 의도한 파일만 stage하고 staged diff를 검토한다.

```bash
git add <intended-files>
git diff --cached --stat
git diff --cached --check
git commit -m "<short change summary>"
```

2. 푸시 권한이 확인된 경우에만 원격 상태를 확인하고 푸시한다.

```bash
git fetch origin
git status --short --branch
git push
```

원격이 앞서 있거나 push가 거부되면 자동으로 rebase, force-push, reset하지 않는다. 현재 branch와 오류를 보고하고 다음 조치를 결정한다.

## 복구 기준

- 커밋 전 실패: 작업 파일을 유지하고 실패 지점과 재실행 명령을 기록한다.
- 커밋 후 push 전 실패: 로컬 커밋을 유지하고 commit SHA를 보고한다.
- push 후 설치 갱신 실패: 원격 변경을 되돌리지 말고 설치 오류를 별도 문제로 다룬다.
- 공개된 커밋을 되돌려야 한다면 새 revert commit을 사용한다. 공유 이력을 다시 쓰지 않는다.
