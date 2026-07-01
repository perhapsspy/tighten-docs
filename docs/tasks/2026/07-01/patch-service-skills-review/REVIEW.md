# Patch-Service 문서 스킬 리뷰

## 기준

- 원격: `Conalog/patch-service` `main`
- 커밋: `30f6b606c395e4f41e295437699a1b213ed4dda6`
- 범위: `.agents/skills/**`
- 대상: `context-driven-development`, `coupling-analysis`, `documentation-and-adrs`, `domain-analysis`, `hads`, `modular-decomposition`, `modular-design-principles`
- 비교 질문: `tighten-docs`의 목적 중심 교정 계약과 유사한가, 아니면 참고할 만한 경계/절차/문서 소유 모델이 있는가.

## 통합 결론

현재 `tighten-docs` 본문을 바로 더 고칠 필요는 낮다. `patch-service` 스킬들은 문서 생성, 컨텍스트 산출물 관리, 아키텍처 분석, HADS 포맷 변환처럼 `tighten-docs`의 선택 대상 교정 범위를 넘는 기능을 많이 포함한다. 참고할 것은 실행 범위가 아니라 판단 언어다.

- 문서가 맡은 단일 역할과 독자 행동을 먼저 잡는다.
- 같은 단어라도 문서 역할이 다르면 같은 문서에 섞지 않는다.
- 사실, 필요한 맥락, 불확실한 주장, 작업 편의용 기록을 구분한다.
- 좋은 정보라도 선택된 대상이 소유하지 않으면 삭제하거나 후속 후보로만 남긴다.
- 사용자가 명시하지 않으면 새 문서, 문서 패키지 재설계, 기준 소스 감사, task-state/handoff 작성, 구현 계획으로 확장하지 않는다.

이 결론은 현재 `tighten-docs` 계약과 대체로 일치한다. `skills/tighten-docs/SKILL.md`는 이미 선택된 대상만 교정하고, line edit 전에 `single role`, `primary subject`, `reader action`, `owned promise`를 확인하며, 새 문서 작성/소스 감사/task-state/문서 패키지 재구조화/구현 계획 변경을 중단 조건으로 둔다.

## 스킬별 메모

### `documentation-and-adrs`

- 역할: ADR, README, API 문서, changelog, agent-facing docs까지 포함하는 문서 생성/유지 스킬이다.
- 유사점: “코드가 보여주는 what보다 문서가 설명하는 why”를 강조하고, 명백한 코드 반복 설명을 피한다.
- 참고점: 이미 있는 ADR이나 결정 문서를 교정할 때는 why, 결정 상태, 대안, 결과가 그 문서의 owned promise인지 먼저 확인해야 한다.
- 비채택: ADR 템플릿, 순번, lifecycle, README/API/checklist 생성 규칙은 `tighten-docs`에 넣으면 새 문서 작성과 문서 체계 설계로 번진다.
- 증거: `<patch-service>/.agents/skills/documentation-and-adrs/SKILL.md` lines 8-21, 36-90, 240-278.

### `hads`

- 역할: HADS 포맷의 Markdown 기술 문서를 읽고, 생성하고, 검증하는 스킬이다.
- 유사점: 권위 사실, 인간 맥락, 검증된 실패, 미확인 추정을 분리해 AI가 읽을 범위를 줄인다.
- 참고점: 교정 중 “현재 사실”, “필요한 맥락”, “불확실한 주장”, “검증된 실패”가 섞여 방어적 문장으로 늘어나는지 볼 수 있다.
- 비채택: `[SPEC]`, `[NOTE]`, `[BUG]`, `[?]` 태그, AI manifest, version header, changelog, validator는 포맷 변환/새 구조 강제라 범위 밖이다.
- 증거: `<patch-service>/.agents/skills/hads/SKILL.md` lines 11-27, 31-46, 81-113, 160-189.

### `context-driven-development`

- 역할: `conductor/` 아래 `product.md`, `tech-stack.md`, `workflow.md`, `tracks.md` 같은 context artifact를 만들고 유지한다.
- 유사점: artifact마다 “무엇을 정의하는가”가 다르며, 문서가 AI 행동과 팀 정렬을 바꾸는 계약이라고 본다.
- 참고점: `product.md = WHAT/WHY`, `workflow.md = HOW to Work`처럼 문서별 질문을 먼저 잡는 방식은 `tighten-docs`의 target role 확인과 맞다.
- 비채택: artifact 생성, `conductor/` 구조, `/conductor:setup`, artifact 동기화, stakeholder confirmation, CI/context validation은 새 문서/작업 상태 관리로 번진다.
- 증거: `<patch-service>/.agents/skills/context-driven-development/SKILL.md` lines 3-9, 26-44, 46-119, 262-328.

### `modular-design-principles`

- 역할: 모듈 경계, public surface, ownership, explicit contracts, state isolation, compliance signals를 다루는 아키텍처 원칙 스킬이다.
- 유사점: 문서에도 public surface와 내부 설명의 경계가 있다. 대상 문서가 자기 역할 밖의 정책, 상태 저장, 라우팅, 구현 계획을 끌어오면 boundary leak로 볼 수 있다.
- 참고점: “신호이지 증거는 아니다”라는 리뷰 태도는 유용하다. 교정 중에도 역할 밖 신호를 봤다고 곧바로 문서 패키지 재설계를 시작하면 안 된다.
- 비채택: bounded context 생성 절차, split/merge 기준, severity tier, 모듈 의존성/장애 독립성 원칙은 아키텍처 감사로 확장된다.
- 증거: `<patch-service>/.agents/skills/modular-design-principles/SKILL.md` lines 3-18, 39-69, 73-86, 141-188.

### `domain-analysis`

- 역할: 비즈니스 언어 기준으로 subdomain과 bounded context를 찾는 전략 분석 스킬이다.
- 유사점: 코드 구조보다 비즈니스 언어를 먼저 보듯, 문서 교정도 문장 polish보다 문서 목적 언어와 독자 행동을 먼저 봐야 한다.
- 참고점: “same term, different meaning”은 문서에도 적용된다. `status`, `plan`, `handoff` 같은 단어가 README, 작업 로그, 실행 계획에서 서로 다른 독자 행동을 가리키면 한 문서에 섞지 않는다.
- 비채택: Core/Supporting/Generic taxonomy, cohesion 점수, bounded context 분석 자체는 문서 교정 계약에 과하다.
- 증거: `<patch-service>/.agents/skills/domain-analysis/SKILL.md` lines 1-19, 37-83, 304-323, 380-425.

### `coupling-analysis`

- 역할: 모듈 결합을 strength, distance, volatility로 분석하고 결합이 문제인지 판단하는 감사 스킬이다.
- 유사점: 문서도 목적 간 결합이 생긴다. README가 소개, 설치, 정책, 작업 상태, 결정 로그를 모두 떠안으면 문서 결합이 커진다.
- 참고점: public contract와 accidental dependency를 구분하는 질문이 유용하다. 문장이 대상 문서의 계약인지, 우연히 남은 설명인지 가른다.
- 비채택: 결합 수식, severity taxonomy, dependency graph, volatility 분석은 문서 교정 스킬에 넣기에는 무겁다.
- 증거: `<patch-service>/.agents/skills/coupling-analysis/SKILL.md` lines 1-24, 39-80, 220-227, 297-330, 416-422.

### `modular-decomposition`

- 역할: component inventory, common domain detection, flattening, coupling, domain grouping을 순서대로 실행하는 monolith decomposition 라우터다.
- 유사점: 가장 직접적인 참고점은 ordered pass다. 문서 교정에서도 목적 식별, 역할 충돌/중복 감지, 소유 위치 판단, 축약/삭제 순서가 자연스럽다.
- 참고점: 사용자가 일부 단계만 원하면 생략된 단계의 한계를 말한다는 규칙은 유용하다. 단순 축약만 요청받았으면 문서 소유권 재설계까지 하지 않아야 한다.
- 비채택: namespace refactor, domain grouping 확정, service extraction next steps, roadmap 생성은 `tighten-docs` stop condition에 걸린다.
- 증거: `<patch-service>/.agents/skills/modular-decomposition/SKILL.md` lines 1-27, 55-78; `<patch-service>/.agents/skills/modular-decomposition/references/pattern-03-flattening.md` lines 79-103; `<patch-service>/.agents/skills/modular-decomposition/references/pattern-05-domain-grouping.md` lines 76-83, 143-151, 710-726.

## 참고 후보

우선순위:

1. `modular-decomposition`: 목적 식별 -> 역할 충돌/중복 감지 -> 소유 위치 판단 -> 축약/삭제 순서.
2. `modular-design-principles`: 문서 역할 밖 내용을 boundary leak로 보는 사고.
3. `hads`: 사실, 맥락, 검증된 실패, 불확실한 주장을 구분하는 사고.
4. `domain-analysis`: 같은 단어라도 문서 역할/독자 행동이 다르면 섞지 않는 기준.
5. `documentation-and-adrs`: 결정 문서류에서 why를 무조건 삭제하지 않도록 owned promise를 확인하는 기준.

후속으로 정말 한 문장만 후보화한다면 다음 정도가 안전하다. 다만 현재 `SKILL.md`의 역할/소유 약속 확인 규칙이 이미 대부분 흡수하고 있으므로 즉시 반영할 필요는 낮다.

```text
Before editing, separate owned facts, necessary context, and uncertain claims; tighten or remove only what the target document role can own.
```

## 제외 또는 비채택 후보

- ADR 생성 템플릿, status/lifecycle, alternatives/consequences 강제 구조.
- HADS 포맷 변환, AI manifest, changelog, validator.
- `conductor/` artifact 생성, 동기화, CI validation.
- DDD taxonomy, bounded context 분석, cohesion 점수.
- coupling 수식, dependency graph, volatility 분석.
- namespace/domain refactor, extraction roadmap, implementation next steps.
- 문서 패키지 전체 정보구조 재설계.
- 기준 소스 감사, 전역 용어 정규화, 문서 간 정책 일관성 확보.
- task-state/handoff 문서 생성 또는 갱신.

## 후속 계약에서 피할 표현

다음 표현은 `tighten-docs`의 선택 대상 교정 범위를 넘기 쉬우므로, 후속 스킬 계약으로 옮기지 않는다.

- “관련 문서 전체의 소스오브트루스를 감사한다.”
- “문서 패키지의 역할과 정보구조를 재설계한다.”
- “ADR 형식으로 배경, 대안, 결과, 상태를 정리한다.”
- “handoff/task-state 문서를 생성하거나 갱신한다.”
- “구현 계획과 후속 작업 항목을 도출한다.”
- “용어 체계를 전역으로 정규화한다.”
- “문서 간 정책 일관성을 확보한다.”
- “누락된 맥락을 보완해 새 설명을 추가한다.”
- “불확실한 사실을 조사해 확정한다.”
- “스킬 간 공통 프레임워크로 통합한다.”

## 현재 권고

이번 감사만으로는 `skills/tighten-docs/SKILL.md`를 추가 수정하지 않는다. 후속 사용자 지시가 있으면 `참고 후보`의 한 문장 후보를 기준으로 다시 검토하되, 새 구조/템플릿/감사/계획 생성으로 넓히지 않는지 먼저 확인한다.
