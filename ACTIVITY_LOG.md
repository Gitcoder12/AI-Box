# AI-Box — Activity Log

**Snapshot:** 2026-11-13

## Verified history

No portfolio source-edit PR or issue was recorded in this pass. README describes a BYOK static frontend with multiple provider panels and browser-local workspace state.

## Current scope

Static frontend with provider panels for Claude, Gemini and DeepSeek, user-supplied API keys, shared prompt/system instruction, parallel responses and browser-local workspace state. Because it is client-side and BYOK, keys can be exposed to browser extensions, developer tools or local storage if handled poorly; inspect storage and network paths before public use.

## Append-only record

| Date | Contributor / agent | Issue / PR | Provider/files | Validation method | Result | Evidence / limitations |
|---|---|---|---|---|---|---|
| YYYY-MM-DD | name | link | provider and paths | exact command, browser and fixture | pass / fail / not run | evidence |

Record browser/runtime, provider model/version, latency measurement method and errors. Never add real API keys to logs or test fixtures.
