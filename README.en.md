# Tighten Docs

[한국어](README.md) | [English](README.en.md)

## What does it fix?

Use `tighten-docs` as the default quality pass whenever an agent creates, revises, or reviews human-authored documentation. It makes selected prose shorter and clearer, separates current guidance from drafts, logs, and stale material, and removes rejected decisions instead of reviving them as statements such as “not supported.”

## Quick Start

**Install**

```bash
npx skills add perhapsspy/tighten-docs
```

Or copy `skills/tighten-docs` into your agent skills directory.

**Use**

```text
Use $tighten-docs to tighten this document against my last correction.

Use $tighten-docs to turn the removal request in this diff into actual deletion.

Use $tighten-docs while drafting this document so the prose starts concise and stays in the required language.

Use $tighten-docs on the README changed with this feature so it states only the current reader action directly.

Use $tighten-docs to review and delete every trace that preserves the removed hosted-mode decision as negation or a warning.

Use $tighten-docs to organize duplicate owners and stale routes across this README, design document, and runbook package.

Use $tighten-docs to review this migration documentation package without editing it, leading with issues and risks.
```

## Use When

- An agent creates, revises, or reviews settled human-authored documentation
- Documentation prose changes as part of a code, product, or operational task
- Human-authored wording or structure changes even without a large rewrite
- The correction should become body text
- Drafting should start with direct prose, the required language, and cleanup of duplicate routing
- Removal requests are reappearing as warnings, routing, or defensive wording
- A rejected decision survives as “not supported,” “no longer planned,” comparison, or exception text
- The document language must stay intact while identifiers, paths, and product names remain unchanged
- A selected documentation package has conflicting entrypoints, reader routes, or current owners
- Document boundaries are causing fragmentation, link mazes, or competing canonical guidance
- Evidence, logs, drafts, or archived material look like current canon
- A runbook needs its preconditions, stop conditions, approval boundary, evidence, rollback, and recovery checked

## How it works

- Apply the latest correction directly to the final prose.
- Turn removal requests into actual deletion instead of warnings or workarounds.
- Ask whether a sentence would still be needed if the discarded option had never existed; if not, delete its denial, comparison, and rationale too.
- Separate current guidance from logs, drafts, and stale material.
- Keep one current answer for each decision or plan.
- Split only material with an independent use; keep a coherent contract or procedure together.
- Do not invent facts or policy that the source does not support.

## Support

[![Buy Me A Coffee](https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png)](https://www.buymeacoffee.com/perhapsspy)

## License

[MIT](LICENSE)
