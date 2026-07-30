# Kodem

Kodem Security is an AI-native application security platform built on runtime intelligence, founded in 2021 by Aviv Mussinger, Idan Bartura, and Pavel Furman. Kodem connects code analysis, runtime evidence, AI reasoning, and runtime protection into a single system so security teams prioritize and fix what is actually exploitable in production rather than triaging every theoretical finding.

The platform spans runtime-powered software composition analysis (SCA) across transitive and OS-level dependencies, native SAST powered by Opengrep with 1,000+ rules plus secrets detection, and Application Detection & Response (ADR) that detects exploit attempts at the application layer without signatures. Its AI layer, Kai, is grounded in function-level runtime evidence to accelerate triage, prioritization, and repository-grounded remediation. Kodem is SOC 2 Type II.

- Website — https://www.kodemsecurity.com/
- Pricing — https://www.kodemsecurity.com/pricing
- Blog — https://www.kodemsecurity.com/resources
- Status — https://status.kodemsecurity.com/
- Application / sign-in — https://app.kodemsecurity.com/

Backed by: greylock

## API surface

Kodem operates a real API at `https://api.kodemsecurity.com`, but it is **entirely closed to unauthenticated discovery**. Every path probed — including `/openapi.json`, `/swagger.json`, `/docs`, `/redoc`, `/health`, `/v1` and `/.well-known/*` — returns HTTP 401 with a `{"detail":"Unauthorized"}` JSON envelope. The CORS preflight advertises an `x-kodem-apikey` request header alongside `authorization`. No OpenAPI document, public API reference, or authentication guide is published; product documentation sits behind the application login at `docs.kodemsecurity.com`.

## Artifacts

| Artifact | Path | Method |
|---|---|---|
| llms.txt | `llms/kodem-llms.txt` | searched (verbatim, provider-authored) |
| Well-known index | `well-known/kodem-well-known.yml` | searched |
| Authentication | `authentication/kodem-authentication.yml` | probed |
| Conformance / compliance | `conformance/kodem-conformance.yml` | searched |
| Lifecycle | `lifecycle/kodem-lifecycle.yml` | searched |
| Domain security | `security/kodem-domain-security.yml` | probed |

Not present, and deliberately not fabricated: OpenAPI, packages/SDKs (the npm `kodem-cli` package is an unrelated 2019 deployment tool from a different "Kodem"), MCP server, CLI, sandbox, changelog, error catalog, OAuth scopes, vulnerability-disclosure program, and trust center — none are published on Kodem's public surface.
