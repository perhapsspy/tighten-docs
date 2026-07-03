---
name: tighten-docs
description: Use to tighten, draft, revise, or clean up documentation prose when a selected, named, concretely requested, or just-created document or diff needs concise final wording, including after user or reviewer feedback and during mixed-language cleanup. Apply the latest correction or drafting constraint as final text by writing, shortening, or clarifying prose, deleting rejected or stale material, removing defensive or explanatory bloat, keeping legacy compatibility claims only when proven, enforcing the required prose language and locale, and preserving real code/API identifiers, paths, commands, product names, and domain terms. Stay scoped to prose on the concrete target; hand off source-of-truth or ownership audits, decisions about new documentation surfaces, task-state or handoff docs, broad documentation restructuring, translation-only work, and implementation planning.
---

# Tighten Docs

## Purpose

Guide documentation prose while writing or editing a concrete target. Make the target shorter, clearer, and faithful to the latest correction or drafting constraint.

This skill is for prose discipline during documentation writing and corrective editorial passes. Its scope is the target's wording, density, required language, and cleanup; source-of-truth selection, document ownership, new documentation surfaces, task state, and documentation architecture belong to other workflows.
This includes language-expression cleanup when the target already has a required prose language and contains extra prose in another language.

## Rules

- Stay with the selected, named, concretely requested, or just-created target. If the target document, requested output, or diff is unclear, ask briefly for the target surface.
- Before line edits, identify the target's single role, primary subject, reader action, and owned promise.
- Turn the latest correction or drafting constraint into final text.
- When drafting new prose for an already concretely requested target, apply these rules before writing.
- Delete rejected, stale, or excluded material; keep warning or rationale text only when the target owns that purpose.
- Add legacy compatibility, fallback, exception, or routing language only when the selected target, correction, or drafting constraint proves it is still required.
- Expand local corrections into cross-document policy only when the user explicitly asks for that policy.
- Remove defensive explanations, duplicate routes, process narration, agent-convenience notes, apology-style prose, and meta-comments about the edit; keep them only when the selected target owns that purpose.
- Determine the required prose language and locale from the selected target, repository or user instruction, latest correction, and drafting constraint. If it is clear, rewrite kept prose into that language and delete duplicated, stale, or extra prose in any other language. If it is unclear or conflicting, ask briefly.
- Preserve literal terms that should remain unchanged: code identifiers, API names, file paths, commands, product names, domain terms, quoted protocol text, and externally owned labels.
- Keep current facts that remain relevant and align with the correction or drafting constraint.

## Editing Pass

1. Read the selected target or requested output and the latest correction or drafting constraint.
2. Establish the target's single role, primary subject, reader action, and owned promise.
3. Identify the required prose language/locale and literal terms that must remain unchanged.
4. For new prose on a concretely requested target, write final-state text directly from that role, reader action, language, and constraint.
5. For existing prose, mark each sentence as keep, replace, delete, compress, or language-fix based on whether it serves that role and reader action.
6. Replace stale wording with the corrected final state.
7. Delete rejected material, defensive prose, imagined legacy requirements, duplicated, stale, or extra non-required-language prose, agent-convenience notes, and process narration.
8. Rewrite kept prose that uses a non-required language into the required prose language.
9. Merge repeated explanations into one short statement.
10. Re-read for one clear role, final-state text, current facts, required-language prose, and reviewable density.

## Stop Conditions

Stop and ask or hand off when the task is pure translation/localization, requires choosing the source of truth, deciding document ownership, restructuring a documentation package, designing task state or handoff docs, deciding whether to create a new documentation surface, or changing implementation plans.
