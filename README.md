# Tighten Docs

[한국어](README.md) | [English](README.en.md)

## 요약

`tighten-docs`는 이미 선택되었거나 구체적으로 요청된 문서나 diff를 작성 중이거나 사용자/리뷰어의 수정 요청을 반영해 더 짧고 정확하게 고치는 스킬입니다.

핵심은 다음 기준입니다.

- 최신 지적을 최종 문장으로 반영한다.
- 작성 제약을 처음부터 본문에 적용한다.
- 삭제 요청은 실제 삭제로 반영한다.
- 레거시 호환 요구는 확인된 경우만 남긴다.
- 문서의 요구 언어와 로캘을 지킨다.

## 빠른 시작

**설치**

```bash
npx skills add perhapsspy/tighten-docs
```

혹은 `skills/tighten-docs` 폴더를 에이전트 스킬 디렉터리에 직접 복사합니다.

**바로 사용**

```text
$tighten-docs 이 문서를 방금 지적한 내용대로 더 짧게 고쳐줘.

$tighten-docs 이 diff에서 삭제 요청을 실제 삭제로 반영해줘.

$tighten-docs 이 문서 초안을 요구된 본문 언어와 짧은 최종 문장으로 작성해줘.
```

## 이런 때 사용

- 작성하거나 고칠 문서나 diff가 이미 구체적으로 정해져 있을 때
- 지적을 본문에 바로 반영해야 할 때
- 초안 작성 시점부터 직접적인 문장, 요구 언어, 중복 라우팅 정리를 적용해야 할 때
- 삭제 요청이 경고, 라우팅, 방어적 문구로 되살아날 때
- 문서 언어는 지키고 코드 식별자, 경로, 제품명은 그대로 둬야 할 때

## 지원

[![Buy Me A Coffee](https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png)](https://www.buymeacoffee.com/perhapsspy)

## 라이선스

[MIT](LICENSE)
