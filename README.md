# Klisten DeadlineEngine for Gemini CLI — v0.1.0

Calculate and compare indicative UTC dates from explicit intervals.

Compute supported notice, renewal, cancellation, limitation and opt-out interval clauses from a caller-provided event timestamp. Months and years use documented approximations. Compare before/after contracts using the same event. No legal opinion, arbitrary legal interpretation, reminders, persistence, email or wallet charge.

## Authentication and scope

Endpoint: https://api.klisten.co.kr/mcp/deadlineengine
Create your own dedicated key at https://klisten.co.kr/app with `deadline:compute`, `deadline:diff`. Configure the sensitive extension setting `KLISTEN_DEADLINEENGINE_API_KEY`. Never place credentials in prompts, arguments, files in this package or public repositories. No administrator or shared operator key is supplied. API key authentication only; no OAuth flow is claimed.

Prerequisites: Use documented synthetic contract intervals; no private contract needed.

## Installation and removal

From the parent directory run `gemini extensions install ./klisten-deadlineengine`. Enter your key only in the sensitive setting. Inspect `/mcp` in Gemini CLI. Uninstall with `gemini extensions uninstall klisten-deadlineengine`; separately revoke the key in your account. Uninstall does not delete hosted data. If secure settings are unavailable, stop rather than hardcode a key.

Expected tools: `deadline_compute`, `deadline_diff`.

## Grounded examples

- Request: Calculate notice 30 days from January 1, 2026 UTC.
  Tool(s): deadline_compute. Expected: January 31, 2026 UTC; no notification.
- Request: Compare explicit notice 30 days against notice 45 days at the same event.
  Tool(s): deadline_diff. Expected: Indicative date comparison using provided intervals.
- Request: Try a negative or fractional duration.
  Tool(s): deadline_compute. Expected: Unsupported input rejected.

## Limits and verification

This is an integration package, not a purchase, paid subscription, safety certification or service SLA. Existing product prerequisites and pricing apply; installation itself does not charge or replenish credit. Do not infer that every underlying operation is free. No money transfer or paid execution is authorized by installing. Any paid action or data mutation requires the account holder’s authorization. Missing records and denied access are errors, not successful demonstrations.

Gemini CLI 0.63.0 native MCP library authenticated discovery: PASS (2026-10-13). This was a scripted library harness, not the interactive Gemini application or a model conversation. Gemini conversation tools/call: NOT_VERIFIED. Local installation/removal evidence is recorded separately and does not prove service or conversation success. Prior revoked validation keys cannot be reused. GitHub distribution and the gallery discovery topic do not establish gallery listing or approval.

This release is a free limited beta; no wallet debit is implemented for these exposed beta functions.

Documentation: https://klisten.co.kr/deadlineengine.html
Privacy: https://klisten.co.kr/privacy.html
Terms: https://klisten.co.kr/terms.html
Support: klisteninc@gmail.com

## Required Gemini 0.63 environment setting

Gemini 0.63 redacts API_KEY environment values from MCP transport headers by default. Explicitly allow only this extension's variable in your isolated Gemini profile settings.json, merging without removing existing settings:

```json
{"security":{"environmentVariableRedaction":{"allowed":["KLISTEN_DEADLINEENGINE_API_KEY"]}}}
```

This file contains the variable name only, never the key. Keep the key in the sensitive extension setting. Do not disable redaction globally or allow all environment variables. Without this narrow exception, authentication returns 401. After installation and this configuration, inspect `/mcp` before any use.

Latest safe native-library call verification: PASS. deadline_compute
