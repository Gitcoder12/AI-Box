# AI Box
Compare Claude, Gemini & DeepSeek side-by-side in one tab. BYOK, memory per model, zero backend. Single HTML file.
Live: https://gitcoder12.github.io/AI-Box/


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


---

## Comparison with Existing Open-Source Projects

AI Box is documented as a single-page, bring-your-own-key interface for comparing several model providers side by side, with separate per-model context and no application backend. These projects provide relevant multi-provider chat-interface comparisons.

| Project | Established focus | Relationship to AI Box |
|---|---|---|
| [Open WebUI](https://github.com/open-webui/open-webui) | Self-hosted AI interface with model connections, tools and broader workspace features | Much broader self-hosted platform; AI Box is intentionally a smaller browser-only comparison surface. |
| [LibreChat](https://github.com/danny-avila/LibreChat) | Multi-provider AI chat application with accounts, tools and integrations | More extensive application and integration ecosystem; AI Box focuses on quickly comparing provider responses in one tab. |
| [LobeChat](https://github.com/lobehub/lobehub) | Multi-provider AI chat framework with plugins and knowledge features | Richer extensible chat experience; AI Box's intended distinction is minimal setup and separate model conversations. |

### Where AI Box is different
- **Side-by-side comparison:** its stated core workflow puts multiple model responses next to one another for the same prompt.
- **Bring your own keys:** provider credentials are supplied by the user rather than managed through a hosted backend.
- **Single-file simplicity:** the README describes a self-contained browser app with no backend service to deploy.

### Where established projects are stronger
Open WebUI, LibreChat and LobeChat provide richer authentication, model management, tools, persistence and deployment options. AI Box should not claim stronger privacy merely because it has no backend: browser storage and client-side API calls still expose keys to scripts in the same origin and the user's browser profile.

### Security and evaluation requirements
Explain the localStorage key-storage risk prominently, provide a clear key-removal action, avoid shared-device use, and handle provider errors/timeouts/rate limits. Any “winner” score must be labelled as a heuristic unless backed by a documented, independent evaluation protocol. This is a scope comparison, not a model-quality benchmark.
