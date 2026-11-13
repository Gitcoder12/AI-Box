# Independent Model Audit Router — AI-Box

**Revision date:** 2026-11-13

## Mandatory data and evidence policy
- Never replace real or maintainer-provided data with invented, generated, synthetic or placeholder records.
- Trace sources, licences, collection dates and Git history before changing datasets.
- If data cannot be verified, preserve it and mark it unknown/unverified. Never invent a substitute.
- Synthetic examples are permitted only when labelled and isolated from runtime/production data.
- Do not fabricate people, companies, official records, citations, metrics, benchmark scores, customers, deployments or endorsements.
- Tests pass only when run successfully on the exact commit being reviewed.

## README preservation
Recover and preserve the last maintainer-authored README from Git history. Do not rewrite or replace it. Append any AI-generated explanation only as a dated, clearly labelled secondary section at the very bottom.

## Independent reviewers
1. Data provenance and integrity.
2. Code, architecture, API and implementation.
3. Security, privacy, dependencies and trust boundaries.
4. Build, tests, CI and reproducibility.
5. README history, licensing, attribution and links.
6. Career/research-facing claims and evidence.

## Audit steps
1. Record repo URL, default branch, exact HEAD, fork status and current PR heads.
2. Classify each relevant change as merged, open, closed-unmerged, reverted or unverified.
3. Inventory runtime data, fixtures, generated output, external APIs and provenance.
4. Compare README with its pre-AI historical version.
5. Run documented build/lint/test commands on exact commits; check CI for suppressed failures.
6. Inspect security, privacy, UX, accessibility, errors, edge cases and performance.
7. Verify public claims and links; employer matches are potential skills fit, not customer or partner claims.
8. Publish evidence-based findings before making changes.

## Finding format
Severity (**P0/P1/P2/P3**), exact file/line, reproduction, expected vs actual, evidence and commit SHA, confirmed/suspected/unverifiable status, minimum fix, regression test, and impact on data/README history.

## Merge gate
- [ ] No fabricated data presented as real.
- [ ] Real/user-provided data preserved; no silent substitution.
- [ ] Synthetic examples labelled and isolated.
- [ ] Original README preserved; AI notes at bottom only.
- [ ] Exact-head tests and CI verified; failures disclosed.
- [ ] No secrets, private personal details, classified or confidential material.
- [ ] Licensing and attribution retained.
- [ ] Independent second review and maintainer approval recorded.

Repository: **AI-Box**. Do not infer features from name or roadmap. Do not merge, delete, force-push, overwrite data or alter original README during an audit. The repository owner has final approval.
