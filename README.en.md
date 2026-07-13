# Tighten Docs

[한국어](README.md) | [English](README.en.md)

## What does it fix?

`tighten-docs` fixes documentation that is hard to enter or gives the same decision different answers in different files. It makes selected prose shorter and clearer, then separates current guidance from drafts, logs, and stale material.

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

Use $tighten-docs to organize duplicate owners and stale routes across this README, design document, and runbook package.

Use $tighten-docs to review this migration documentation package without editing it, leading with issues and risks.
```

## Use When

- The document or diff to write or edit is already selected or concretely requested
- The correction should become body text
- Drafting should start with direct prose, the required language, and cleanup of duplicate routing
- Removal requests are reappearing as warnings, routing, or defensive wording
- The document language must stay intact while identifiers, paths, and product names remain unchanged
- A selected documentation package has conflicting entrypoints, reader routes, or current owners
- Document boundaries are causing fragmentation, link mazes, or competing canonical guidance
- Evidence, logs, drafts, or archived material look like current canon
- A runbook needs its preconditions, stop conditions, approval boundary, evidence, rollback, and recovery checked

## How it works

- Apply the latest correction directly to the final prose.
- Turn removal requests into actual deletion instead of warnings or workarounds.
- Separate current guidance from logs, drafts, and stale material.
- Keep one current answer for each decision or plan.
- Split only material with an independent use; keep a coherent contract or procedure together.
- Do not invent facts or policy that the source does not support.

## Support

[![Buy Me A Coffee](https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png)](https://www.buymeacoffee.com/perhapsspy)

## License

[MIT](LICENSE)
