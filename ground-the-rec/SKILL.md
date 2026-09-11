---
name: ground-the-rec
description: Ground a recommendation in this repo before proposing or implementing it. Use when starting to implement, add, or build a feature (구현, 추가), or when choosing a library, API, pattern, or version.
---

# Ground the rec

A rec is **grounded** when every applicable gate has checkable evidence. Ground before the first rec or the first edit. User asked for code → ground, then implement in the same turn.

Gates are pass conditions, not agents. The main agent runs them. One scout only when Fit needs a tour of unknown code. Paths stays on the main agent.

Order: **Fit**, then **Stale** if a library/API/version remains, then **Paths** if the rec has runtime behavior. Skip a gate that does not apply; do not announce the skip.

## Fit

What this repo already does in this layer.

Done: the rec cites a path or symbol it follows, or states there is no precedent in this layer. A name-search miss is not "no precedent" — look at the neighboring feature in the same layer, or the data/auth pattern this would sit on.

Fit is this repo's current convention. The habit this task is here to change is not a precedent.

## Stale

Applies when the rec names a library, API, or version.

Done: the rec cites the lockfile/manifest version, or the official current docs. Training recall is not a source.

## Paths

Applies when the rec has runtime behavior.

Done: the rec names the success path and the failure/empty/auth/idempotency paths that exist here, and any deferred path with a reason. Design coverage, not a test matrix.

## Output

Cite evidence inside the rec or first edit. No gate report. An uncited applicable gate is open.
