# AI Box
Compare Claude, Gemini & DeepSeek side-by-side in one tab. BYOK, memory per model, zero backend. Single HTML file.
Live: https://gitcoder12.github.io/AI-Box/


## Open AI Box locally (VS Code)

1. Clone the repository and open it in VS Code:

```bash
git clone https://github.com/Gitcoder12/AI-Box.git
cd AI-Box
```

2. Start a local static web server:

```bash
python -m http.server 8000
```

3. Open **http://localhost:8000** in your browser.
4. Keep the terminal running while using the app; press **Ctrl+C** to stop the server.

No npm installation or build step is required. Provider API calls need your own API keys. The current app stores keys in browser `localStorage`; use only a trusted/private browser profile and do not use a shared device. Keys are not encrypted by the app.

---

## AI-maintained project notes (secondary — 2026-11-13)

This section supplements the maintainer-authored README above. The original text has been restored verbatim from Git-history baseline `10fcb828b96806127a7bbb4537bcd3b184f6cc48`; this addendum does not replace or certify the original claims.

- The current source tree, runtime data and tests are the implementation source of truth. A roadmap item, draft PR or AI-generated description is not a shipped feature by itself.
- Preserve real and maintainer-provided data. Never silently substitute generated or placeholder data. Clearly label and isolate synthetic fixtures.
- Mark unverified sources, identifiers, metrics, benchmark results and external claims as unknown/unverified rather than guessing.
- Verify setup, execution, tests and public claims against the exact current commit before using this repository in a job, research or academic application.
- See [MODEL_AUDIT_ROUTER.md](MODEL_AUDIT_ROUTER.md) for independent model review instructions and the merge gate.

---

## Engineering Audit & Handover — 2026-11-17

**Reviewed commit:** `259f5b15c2f0b490775a271643d3860f0da7ffe8` (`main`).

### Confirmed findings
- The single-file browser app calls Anthropic, Google Gemini, and DeepSeek APIs directly from the browser.
- API keys are saved in browser `localStorage` under `aibox_keys`. They are not encrypted by this application and can be exposed to scripts executing in the same origin or to anyone with access to that browser profile.
- Provider model IDs are hardcoded in the client. Provider API/model changes can break requests until the page is updated.
- The debate “winner” score is calculated from response length/history size in the inspected client logic; it is not an independent quality or factuality evaluation.

### Next actions
1. Make key storage opt-in and explain the local-browser exposure; provide a clear remove-keys action and avoid storing keys on shared devices.
2. Add request timeouts, cancellation, rate-limit handling, and per-provider error states.
3. Label debate scores as length/comprehensiveness heuristics or replace them with a documented evaluation method.

**Verification status:** static browser-code inspection only; live provider calls, key-handling behavior, and browser tests remain unverified.

---

## Examples Used
- Comparing Claude, Gemini, and DeepSeek on the same question
- Evaluating model answers for accuracy and completeness
- Preserving separate conversation context for each model
