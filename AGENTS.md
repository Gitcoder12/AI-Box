# Agent Instructions — AI-Box

Read README.md, CONTRIBUTING.md and FEATURE_UPGRADE_PLAN.md before changes.

- Never request, expose, store or commit the user's real API keys.
- Use fake fixture keys only in tests; prevent secrets in logs, screenshots and reports.
- Inspect browser storage and request destinations before changing provider integrations.
- Add provider timeout, error and malformed-response tests.
- Preserve BYOK transparency; do not silently proxy prompts or credentials.
- Work on a branch and open a PR; do not merge, deploy or handle external credentials autonomously.
