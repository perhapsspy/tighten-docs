---
name: tighten-docs
description: Use to tighten, revise, or clean up a selected, named, or just-created document or diff after user or reviewer feedback, including unwanted mixed-language prose. Apply the latest correction in place by shortening or clarifying existing text, deleting rejected or stale material, removing defensive or explanatory bloat, avoiding invented legacy compatibility requirements, enforcing the required prose language and locale, and preserving real code/API identifiers, paths, commands, product names, and domain terms. Skip new-document creation, source-of-truth or ownership audits, task-state or handoff docs, broad documentation restructuring, translation-only work, and implementation planning.
---

# Tighten Docs

## Purpose

Tighten a selected, named, or just-created document or diff after user or reviewer correction. Edit the existing target in place so it is shorter, clearer, and faithful to the latest correction.

This skill is for corrective editorial passes, not document generation, source-of-truth audit, task-state storage, or documentation architecture.
This includes language-expression cleanup when the target already has a required prose language and contains unnecessary prose in another language.

## Rules

- Work only on the selected target. If the target document or diff is unclear, ask briefly instead of creating a new surface.
- Before line edits, identify the target's single role, primary subject, reader action, and owned promise.
- Apply the latest correction as final text, not commentary about the correction.
- Delete rejected, stale, or prohibited material instead of preserving it as a warning or rationale.
- Do not add legacy compatibility, fallback, exception, or routing language unless the selected target or correction proves it is still required.
- Do not broaden a local correction into a new cross-document policy unless the user explicitly asks for that policy.
- Remove defensive explanations, duplicate routes, process narration, agent-convenience notes, apology-style prose, and meta-comments about the edit unless the selected target owns that purpose.
- Determine the required prose language and locale from the selected target, repository or user instruction, and latest correction. If it is clear, rewrite kept prose into that language and delete duplicated, stale, or unnecessary prose in any other language. If it is unclear or conflicting, ask briefly.
- Preserve literal terms that should remain unchanged: code identifiers, API names, file paths, commands, product names, domain terms, quoted protocol text, and externally owned labels.
- Keep only current facts that remain relevant and do not conflict with the correction.

## Editing Pass

1. Read the selected target and latest correction.
2. Establish the target's single role, primary subject, reader action, and owned promise.
3. Identify the required prose language/locale and literal terms that must remain unchanged.
4. Mark each sentence as keep, replace, delete, compress, or language-fix based on whether it serves that role and reader action.
5. Replace stale wording with the corrected final state.
6. Delete rejected material, defensive prose, imagined legacy requirements, duplicated non-required-language prose, agent-convenience notes, and process narration.
7. Rewrite kept prose that uses a non-required language into the required prose language.
8. Merge repeated explanations into one short statement.
9. Re-read for one clear role, no resurrected material, no invented legacy requirement, no unnecessary non-required-language prose, and reviewable density.

## Stop Conditions

Stop and ask or hand off when the task is pure translation/localization, requires choosing the source of truth, deciding document ownership, restructuring a documentation package, designing task state or handoff docs, creating a new document, or changing implementation plans.
