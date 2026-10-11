---
name: ground-the-rec
description: Grounds a code change or recommendation in evidence from the current repository before the first edit: the closest existing pattern, the repo's rules (AGENTS.md, decision docs), the dependency versions it actually resolves, and the change's failure paths. Use whenever about to write or propose code in an existing repository (a feature, endpoint, schema or column change, migration, or refactor) and whenever choosing or upgrading a library, API, pattern, or version, even for small changes that look obvious and even when the user does not ask for research. Typical requests include "구현해줘", "추가해줘", "만들어줘", "붙여줘", "넣어줘", "어떻게 하는 게 좋아?", "뭐 쓰면 돼?", "업그레이드", "마이그레이션". Skip pure code explanations, renames, typo or one-line cosmetic edits, and running existing commands.
---

# Ground the rec

A recommendation ("rec") is the approach, library, API, or code you are about to propose or write. It is **grounded** when each applicable check below is backed by evidence the user can verify: a repo path or symbol, a lockfile entry, or an official source link. Recs from memory tend to copy deprecated patterns, target the wrong library version, or skip the error paths this codebase already handles; this skill exists to catch that before the first edit.

Ground before the first rec or edit. If the user asked for code, ground and then implement in the same turn; grounding is not a reason to stop and ask.

Scale effort to the change. A small change that follows an obvious neighbor needs one citation; a new dependency, schema change, or cross-cutting pattern needs every applicable check. Skip checks that do not apply without mentioning them.

Start from the repository root, not just the source folder: list it, read the rule files there (AGENTS.md, CLAUDE.md, CONTRIBUTING, decision or ADR docs) and note the lockfile. They are not always loaded into context automatically. Then run the checks yourself, in order: Fit, Stale, Paths. Hand only the Fit code tour to a subagent, and only when the relevant code is large and unfamiliar.

## 1. Fit: follow what this repo already does

Find the closest existing feature in the same layer (route, service, migration, component) and follow it. Cite its path or symbol, or state that this layer has no precedent. A name search that finds nothing is not proof of no precedent: check the neighboring feature in the same layer and the data, auth, and error handling it sits on.

Before copying a precedent, read the repo's rules: AGENTS.md or CLAUDE.md, CONTRIBUTING, and ADR or decision docs. Existing code can be deprecated or contradict a decision; when it does, say so and follow the rule, not the code. The habit the task is meant to change is never a precedent.

## 2. Stale: verify external behavior at the version this repo uses

Applies when the rec relies on a third-party library, framework, external API, or runtime behavior. Reusing a repo-owned abstraction within its contract is grounded by its own code.

- Existing dependency: take the resolved version from the lockfile (package-lock.json, pnpm-lock.yaml, yarn.lock, bun.lock, uv.lock, poetry.lock, Cargo.lock, go.sum), falling back to the declared range. Confirm the behavior from the installed source or from docs or changelog for that version. Latest docs often describe a different major version.
- New dependency or upgrade: cite current official docs for support and compatibility with this repo's runtime and peer dependencies, and follow the repo's rules for adding dependencies.
- Claims of absence ("no lockfile", "no precedent") need a search that would have found the thing.
- Memory is not a source. When no source is reachable, name the claim that is unverified.

## 3. Paths: design the failure cases, not just the happy path

Applies when the change has runtime behavior. State what happens on success and on each failure path that applies: invalid input, empty or not found, unauthenticated or forbidden, duplicate or retried request. Use the repo's existing handling for them (error type, status codes, middleware). Include paths the change itself creates. Name any deferred path with a reason, and do not invent inapplicable ones; this is design coverage, not a test matrix.

For data or schema changes, also cover existing rows, a fresh database, the upgrade from the current schema, and re-running the migration.

## Output

Put evidence inline where it is used: in the recommendation, or in a short note before the first edit. No separate checklist or gate report, and no grounding comments in code. Example note before editing:

> Following `orders/views.py::OrderCreateView` (serializer validation + `ApiError`), as CONTRIBUTING.md requires. djangorestframework resolves to 3.14.0 (poetry.lock); `UniqueTogetherValidator` checked against the 3.14 docs. Paths: 400 invalid payload, 403 non-owner via `IsOwner`, 409 duplicate via the existing `IntegrityError` handler. Deferred: bulk create (not requested).

An applicable check without evidence is open: say what is unverified and mark the recommendations that depend on it as provisional.
