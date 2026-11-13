# AI Box

**A single-page, bring-your-own-key workspace for comparing multiple language-model providers.**

[![Live Demo](https://img.shields.io/badge/Live-Demo-brightgreen)](https://gitcoder12.github.io/AI-Box/)
[![License](https://img.shields.io/badge/license-see%20LICENSE-lightgrey)](LICENSE)

AI Box provides one browser interface for sending prompts to supported model providers and reviewing their responses side by side. It is a static front-end application with no application backend.

## Features

- Provider panels for Anthropic Claude, Google Gemini, and DeepSeek.
- Bring-your-own API keys.
- Shared prompt and optional system-instruction input.
- Side-by-side model responses.
- Browser-local memory and workspace state.

## Quick Start

Open `index.html` in a modern browser, or serve the repository locally:

```bash
git clone https://github.com/Gitcoder12/AI-Box.git
cd AI-Box
python -m http.server 8000
```

Open `http://localhost:8000`.

## Tech Stack

HTML · CSS · Vanilla JavaScript · Provider HTTPS APIs · Browser Local Storage

## Key and Privacy Notes

The current page stores provider API keys in browser `localStorage` and sends requests directly from the browser to provider APIs. This is convenient for a personal prototype, but local storage is accessible to scripts running on the same origin and is not a secure credential vault. Use only keys with appropriate usage limits, avoid shared/public browser profiles, and revoke keys that may have been exposed. Prompts are sent to the selected provider under that provider's terms.

## Scope and Limitations

There is no server-side key management, team workspace, or centralized usage/billing layer. Provider models and browser-access policies can change, so a provider request may fail even when the interface loads.

## License

See [LICENSE](LICENSE).

---

## Project handbook

- [Activity log](ACTIVITY_LOG.md) · [Feature upgrade plan](FEATURE_UPGRADE_PLAN.md)
- [Company and team fit](COMPANY_FIT.md) · [README explanation draft](README_ADDENDUM_DRAFT.md)
- [README quality checklist](README_QUALITY_CHECKLIST.md)
- [Contributing](CONTRIBUTING.md) · [Agent instructions](AGENTS.md) · [Agent skills](SKILLS.md)
