# Tighten Docs

[한국어](README.md) | [English](README.en.md)

## Summary

`tighten-docs` helps an agent make an already selected or concretely requested document or diff shorter and more accurate while drafting or after user or reviewer correction.

It focuses on these outcomes:

- Apply the latest correction as final text.
- Apply drafting constraints to the body from the start.
- Turn removal requests into actual deletion.
- Keep legacy compatibility claims only when proven.
- Preserve the document's required language and locale.

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
```

## Use When

- The document or diff to write or edit is already selected or concretely requested
- The correction should become body text
- Drafting should start with direct prose, the required language, and cleanup of duplicate routing
- Removal requests are reappearing as warnings, routing, or defensive wording
- The document language must stay intact while identifiers, paths, and product names remain unchanged

## Support

[![Buy Me A Coffee](https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png)](https://www.buymeacoffee.com/perhapsspy)

## License

[MIT](LICENSE)
