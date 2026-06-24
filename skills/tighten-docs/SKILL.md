---
name: tighten-docs
description: Tighten already-selected documentation or diffs after user or reviewer correction. Use when Codex must revise the existing target in place, apply the latest correction, delete rejected content instead of preserving it as warnings, remove defensive or explanatory bloat, avoid inventing legacy compatibility requirements, preserve the user or repository's required language and locale, and keep code/API identifiers intact. Do not use for creating new documentation from scratch, source-owner discovery, task-state storage, or broad documentation restructuring.
---

# Tighten Docs

## Purpose

Tighten an already selected document or diff after user or reviewer correction. Edit the existing target in place so it is shorter, clearer, and faithful to the latest correction.

This skill is for corrective editorial passes, not document generation, source-of-truth audit, task-state storage, or documentation architecture.

## Rules

- Work only on the selected target. If the target document or diff is unclear, ask briefly instead of creating a new surface.
- Apply the latest correction as final text, not commentary about the correction.
- Delete rejected, stale, or prohibited material instead of preserving it as a warning or rationale.
- Do not add legacy compatibility, fallback, exception, or routing language unless the selected target or correction proves it is still required.
- Remove defensive explanations, duplicate routes, process narration, apology-style prose, and meta-comments about the edit.
- Preserve the required document language and locale. Keep real code identifiers, API names, file paths, commands, product names, and domain terms intact.
- Keep only current facts that remain relevant and do not conflict with the correction.

## Editing Pass

1. Read the selected target and the correction.
2. Mark each sentence as keep, replace, delete, or compress.
3. Replace stale wording with the corrected final state.
4. Merge repeated explanations into one short statement.
5. Remove rejected material, defensive prose, imagined legacy requirements, and process narration.
6. Re-read for language consistency and reviewable density.

## Stop Conditions

Stop and ask or hand off when the task requires choosing the source of truth, deciding document ownership, restructuring a documentation package, designing task state or logs, creating a new document, or changing implementation plans.
