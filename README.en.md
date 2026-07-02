# Tighten Docs

[한국어](README.md) | [English](README.en.md)

## Summary

`tighten-docs` helps an agent make an already selected document or diff shorter and more accurate after user or reviewer correction.

It focuses on these outcomes:

- Apply the latest correction as final text.
- Delete rejected material instead of preserving it as warnings.
- Do not invent unproven legacy compatibility requirements.
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
```

## Use When

- The target document or diff is already selected
- The correction should be applied to the body, not explained
- Removal requests are reappearing as warnings, routing, or defensive wording
- The document language must stay intact while identifiers, paths, and product names remain unchanged

## Support

[![Buy Me A Coffee](https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png)](https://www.buymeacoffee.com/perhapsspy)

## License

[MIT](LICENSE)
