# Project Status — AI-Box

**Snapshot date:** 2026-11-16  
**Status type:** Initial documentation and repository-tree assessment  
**Default branch:** main  
**Review completeness:** Partial — not a code audit or release certification

## Project purpose
Single-page, BYOK multi-model comparison interface for Claude, Gemini and DeepSeek, with per-model memory, according to README.

## Current maturity (README-declared or visible scaffolding; not independently verified)
Root contains AI-Box.html and index.html only plus docs. README claims no backend and a GitHub Pages live page; runtime behavior not verified.

## Observed repository structure
AI-Box.html, index.html, README.md, LICENSE and repository guidance.

## Known issues and risks to investigate
Bringing multiple provider API keys into browser-only code raises key-exposure risk: any key entered in a client-side page can be exposed to page scripts, browser extensions or network inspection; verify no hard-coded keys or key persistence. Provider CORS/API terms, model availability, privacy and local memory handling are unverified.

## Recommended next actions
Inspect provider calls and storage; ensure users are warned that BYOK secrets remain client-side and are not transmitted to an owner-controlled backend; avoid hard-coded keys; verify key clearing and local persistence; test API failures/provider changes and prevent transcript leakage.

## Verification record
| Check | Result |
|---|---|
| Default-branch top-level tree | Inspected |
| README | Inspected |
| Deep source review | Not performed |
| Tests / build / runtime | Not run |
| Security / dependency audit | Not run |
| Live deployment / API checks | Not run |
| Independent review | Not performed |

## Change log
- 2026-11-16: Added this initial status snapshot on a review branch. No application code or existing data changed.

> Update this file only after the corresponding inspection or verification has actually been performed. Distinguish observed facts, README claims, hypotheses and unrun checks.