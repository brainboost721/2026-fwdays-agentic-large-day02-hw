# Progress

## Last updated

2026-03-31 — branch `day-2/brainboost721`, HEAD `2eec0f3`. `repomix-compressed.txt` may differ from last commit (see `git status`).

## Overall status

Homework branch **`day-2/brainboost721`**: Excalidraw **app and package source** are the upstream baseline (not modified for homework). **`2eec0f3` (*day 2 init*)** introduced documentation, the Memory Bank, Cursor rule, and repomix-related files in one squashed step. Git history on this clone does **not** list the older per-file documentation commits from day 1; use commit messages above and file contents as the source of truth.

## What has been built

### Tooling and export

- `.cursorignore`, `.repomixignore`, `.gitignore` — limit indexing / packing noise; repomix output paths ignored as configured.
- `repomix-compressed.txt` — large compressed codebase export (~110K+ lines) for documentation and AI context; **working tree may be ahead of HEAD**.

### Memory Bank — `docs/memory/`

| File              | Note                                                                 |
| ----------------- | -------------------------------------------------------------------- |
| `projectbrief.md` | Monorepo scope, delivery shapes, layout                              |
| `systemPatterns.md` | Architecture, layering, state, tests, errors, CI/CD; `#cicd-pipeline` anchor |
| `techContext.md`  | Tooling, commands, path aliases                                      |
| `productContext.md` | Users, journeys, product boundaries                                |
| `decisionLog.md`  | Doc decisions (A); B/C indexes + links to technical files            |
| `activeContext.md` | Session focus, repo state, next steps                               |
| `progress.md`     | This file                                                            |

### Product docs — `docs/product/`

| File                 | Description                          |
| -------------------- | ------------------------------------ |
| `domain-glossary.md` | Canonical terminology              |
| `PRD.md`             | Reverse-engineered product requirements |

### Technical docs — `docs/technical/`

| File                    | Description                                        |
| ----------------------- | -------------------------------------------------- |
| `architecture.md`       | Editor data flow, ownership, file index            |
| `dev-setup.md`          | Environment, commands, troubleshooting             |
| `code-behavior-gaps.md` | Section B detail — doc vs implementation         |
| `implicit-invariants.md` | Section C detail — invariants, hazards, comments |

### Cursor rule

- `.cursor/rules/memory-bank.mdc` — always-apply: Memory Bank read/update protocol and anti-churn guidance for meta-edits.

### Removed / not in tree

- `docs/technical/agent-sharp-edges.md` — superseded by `decisionLog.md` and the B/C technical files (content lives there conceptually).

## What works (application baseline — unchanged)

Inherited from upstream Excalidraw:

- Full editor canvas and tools; embeddable `@excalidraw/excalidraw` API.
- Hosted app: collab (`excalidraw-app/collab/`), share flows, PWA, local-first recovery.
- Localization, export formats, tests and CI as in upstream.

## Known issues

- **Firebase / collab env:** Not in repo; see `docs/technical/dev-setup.md`.
- **`architecture.md` dependency diagram:** `decisionLog.md` Section A notes a possible mismatch: diagram may still show `utils → common` while `packages/utils/package.json` has no `@excalidraw/common` — verify when editing architecture docs.
- **Repomix drift:** Uncommitted changes to `repomix-compressed.txt` until committed or reverted.

## Resolved / stable in current tree

- Memory Bank describes `packages/utils` layering consistently with `packages/utils/package.json` in `systemPatterns.md` (verify after any package.json edits).
- Prettier on docs: if `yarn test:other` fails, run `yarn fix:other` per `docs/technical/dev-setup.md`.

## What's left

1. Complete day-2 homework goals; refresh `activeContext.md` / this file when milestones change.
2. Align `repomix-compressed.txt` with git when ready (commit or discard).

## Commit log (this clone, oldest first)

| Commit    | Date       | Description   |
| --------- | ---------- | ------------- |
| `21bf0a6` | 2026-03-26 | Initial       |
| `70259e8` | 2026-03-26 | checker       |
| `2eec0f3` | 2026-03-31 | day 2 init    |
