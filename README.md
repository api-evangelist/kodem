# Kodem

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
