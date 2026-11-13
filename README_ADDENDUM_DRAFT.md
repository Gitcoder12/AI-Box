# AI-Box — README Explanation Draft

## In plain language

A single browser page where you can send the same prompt to several AI providers and compare their answers side by side.

## How to use it

Choose the model providers you want to compare, enter a prompt, provide the required keys and inspect each response. Explain exactly where a key is sent and whether it is stored.

## Technical explanation

Static frontend with provider panels for Claude, Gemini and DeepSeek, user-supplied API keys, shared prompt/system instruction, parallel responses and browser-local workspace state. Because it is client-side and BYOK, keys can be exposed to browser extensions, developer tools or local storage if handled poorly; inspect storage and network paths before public use.

Document provider adapters, request/response normalisation, concurrency, timeout, error handling, local state and token/cost metadata.

## Security and privacy

Never commit keys. Explain browser trust boundaries and storage behavior. Do not claim that BYOK is automatically secure. If a backend proxy is introduced, document authentication, rate limiting, secret storage and request retention.

## Contributing

See FEATURE_UPGRADE_PLAN.md and CONTRIBUTING.md.
