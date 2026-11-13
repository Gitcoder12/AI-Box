# AI-Box — Feature Upgrade Plan

## Objective

A single browser page where you can send the same prompt to several AI providers and compare their answers side by side.

## P0 — credential safety

- [ ] Ensure provider keys are not persisted by default or included in logs, telemetry, URL parameters or exported workspace data.
- [ ] Review CORS/content-security behavior, provider endpoints, request errors and browser storage for secret leakage.

## P1 — robust provider workflow

- [ ] Add a provider adapter interface with consistent timeout, error and token/cost metadata.
- [ ] Add repeatable comparison runs with saved prompt configuration but no secrets.

## P2 — evaluation

- [ ] Evaluate output quality, latency and cost on a documented task set with user-selected criteria.
- [ ] Add optional safe backend proxy only with explicit auth, per-user limits and secret handling.

## Collaborator work packages

1. Secret-handling audit and tests.
2. Provider adapter contract and failure handling.
3. Consistent comparison UX and run metadata.
4. Reproducible evaluation with prompt set and scoring rubric.

## Definition of done

- [ ] No API key is committed, logged, exported or persisted unexpectedly.
- [ ] Provider errors/timeouts do not break other panels.
- [ ] Comparisons record model/provider metadata and evaluation settings.
- [ ] Performance/quality claims have reproducible evidence.
