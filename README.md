# Tighten Docs

[한국어](README.md) | [English](README.en.md)

## 요약

`tighten-docs`는 이미 선택된 문서나 diff를 사용자/리뷰어 지적 기준으로 더 짧고 정확하게 고치는 스킬입니다.

핵심은 다음 기준입니다.

- 최신 지적을 최종 문장으로 반영한다.
- 빼라고 한 내용은 경고로 보존하지 말고 삭제한다.
- 확인되지 않은 레거시 호환 요구를 새로 만들지 않는다.
- 문서의 요구 언어와 로캘을 지킨다.

## 빠른 시작

**설치**

```bash
npx skills add perhapsspy/tighten-docs
```

혹은 `skills/tighten-docs` 폴더를 에이전트 스킬 디렉터리에 직접 복사합니다.

**바로 사용**

```text
$tighten-docs 이 문서를 방금 지적한 기준으로 더 짧게 고쳐줘.

$tighten-docs 이 diff에서 삭제 요청을 실제 삭제로 반영해줘.
```

## 이런 때 사용

- 이미 고칠 문서나 diff가 정해져 있을 때
- 지적을 설명하지 말고 본문에 바로 반영해야 할 때
- 삭제 요청이 경고, 라우팅, 방어적 문구로 되살아날 때
- 문서 언어는 지키고 코드 식별자, 경로, 제품명은 그대로 둬야 할 때

## 지원

[![Buy Me A Coffee](https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png)](https://www.buymeacoffee.com/perhapsspy)

## 라이선스

[MIT](LICENSE)
