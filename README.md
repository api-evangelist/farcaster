# Farcaster

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
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Farcaster is a decentralised social protocol built on Snapchain, an append-only state machine that stores casts, reactions, follows, and user profile data. The protocol publishes a Hub / Snapchain reference implementation, the Mini Apps SDK (formerly Frames) for distributing interactive apps inside Farcaster feeds, Sign In with Farcaster (SIWF) for authentication, and AuthKit for React-based sign-in. The Warpcast client (now rebranded Farcaster app at farcaster.xyz) is the primary consumer surface. Indexer providers such as Neynar host scaled Hub APIs and value-added read / write / webhook APIs at api.neynar.com.

**Areas:** Farcaster · Social · Decentralized · Protocol · Mini Apps · Frames · Authentication · Web3 · SDK

## Farcaster on APIs.io

Everything profiled for Farcaster is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/farcaster/](https://apis.io/providers/farcaster/)** — or go straight to one of the APIs or properties below.

### APIs (15)

- [Snapchain / Hub API](https://apis.io/apis/farcaster/snapchain/) — Query interface for Farcaster's Snapchain network - read casts, reactions, follows, user data, and verifications by FID; submit signed messages; and run a…
- [Farcaster Mini Apps SDK](https://apis.io/apis/farcaster/mini-apps-sdk/) — JavaScript SDK for building Mini Apps (the evolution of Frames) that run inside Farcaster feeds and clients. Provides host bridge, context, wallet actions,…
- [Sign In with Farcaster (SIWF)](https://apis.io/apis/farcaster/siwf/) — Authentication flow that lets users sign in to third-party apps with their Farcaster identity, returning a verified FID and optional profile data. Backed by…
- [Farcaster AuthKit (React)](https://apis.io/apis/farcaster/auth-kit/) — React toolkit wrapping Sign In with Farcaster - provides hooks and components for the QR-code / deep-link handoff to a Farcaster client and returns the…
- [Neynar Hosted Farcaster API](https://apis.io/apis/farcaster/neynar/) — Third-party indexer providing hosted Hub access, indexed read APIs (users, casts, channels, feeds), write APIs (publish casts, reactions, follows), webhooks…
- [Warpcast / Farcaster Client API](https://apis.io/apis/farcaster/warpcast-api/) — Client-side API exposed by the Warpcast / Farcaster app for client-specific surfaces (channels, mentions, direct casts, mini-app contexts) layered above the…
- [Farcaster Casts API](https://apis.io/apis/farcaster/farcaster-casts-api/) — The Casts API from Farcaster — 4 operation(s) for casts.
- [Farcaster Events API](https://apis.io/apis/farcaster/farcaster-events-api/) — The Events API from Farcaster — 2 operation(s) for events.
- [Farcaster Info API](https://apis.io/apis/farcaster/farcaster-info-api/) — The Info API from Farcaster — 2 operation(s) for info.
- [Farcaster Links API](https://apis.io/apis/farcaster/farcaster-links-api/) — The Links API from Farcaster — 3 operation(s) for links.
- [Farcaster Reactions API](https://apis.io/apis/farcaster/farcaster-reactions-api/) — The Reactions API from Farcaster — 4 operation(s) for reactions.
- [Farcaster Submit API](https://apis.io/apis/farcaster/farcaster-submit-api/) — The Submit API from Farcaster — 3 operation(s) for submit.
- [Farcaster Verifications API](https://apis.io/apis/farcaster/farcaster-verifications-api/) — The Verifications API from Farcaster — 1 operation(s) for verifications.
- [Farcaster On Chain API](https://apis.io/apis/farcaster/farcaster-on-chain-api/) — The On Chain API from Farcaster — 4 operation(s) for on chain.
- [Farcaster User Data API](https://apis.io/apis/farcaster/farcaster-user-data-api/) — The User Data API from Farcaster — 4 operation(s) for user data.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### GraphQL (1)

GraphQL schemas.

- [Farcaster GraphQL Schema](https://apis.io/graphqls/farcaster/farcaster-graphql/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Farcaster Agentic Access](https://apis.io/agentic-access/farcaster/farcaster-agentic-access/)

#### Collections (10)

Postman and Open Collection request collections.

- [Farcaster Snapchain Hub HTTP API](https://apis.io/collections/farcaster/open-farcaster/)
- [Farcaster Snapchain Hub HTTP Casts API](https://apis.io/collections/farcaster/open-farcaster-casts-api/)
- [Farcaster Snapchain Hub HTTP Casts Events API](https://apis.io/collections/farcaster/open-farcaster-events-api/)
- [Farcaster Snapchain Hub HTTP Casts Info API](https://apis.io/collections/farcaster/open-farcaster-info-api/)
- [Farcaster Snapchain Hub HTTP Casts Links API](https://apis.io/collections/farcaster/open-farcaster-links-api/)
- [Farcaster Snapchain Hub HTTP Casts OnChain API](https://apis.io/collections/farcaster/open-farcaster-onchain-api/)
- [Farcaster Snapchain Hub HTTP Casts Reactions API](https://apis.io/collections/farcaster/open-farcaster-reactions-api/)
- [Farcaster Snapchain Hub HTTP Casts Submit API](https://apis.io/collections/farcaster/open-farcaster-submit-api/)
- [Farcaster Snapchain Hub HTTP Casts UserData API](https://apis.io/collections/farcaster/open-farcaster-userdata-api/)
- [Farcaster Snapchain Hub HTTP Casts Verifications API](https://apis.io/collections/farcaster/open-farcaster-verifications-api/)

#### Security (1)

Authentication, trust centre, and vulnerability disclosure.

- [Farcaster Domain Security](https://apis.io/security/farcaster/farcaster-domain-security/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Farcaster Plans Pricing](https://apis.io/plans/farcaster/farcaster-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Farcaster Rate Limits](https://apis.io/rate-limits/farcaster/farcaster-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Farcaster Finops](https://apis.io/finops/farcaster/farcaster-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.farcaster.xyz/)
- [Documentation](https://docs.farcaster.xyz/)
- [Blog](https://farcaster.xyz/blog/)

## API Evangelist rating

**Kin Score 22.9** — emerging · rubric 0.24.0 · scored 2026-10-17

| Facet | Score |
|---|---|
| Discoverability | 60.7 |
| Contract quality | 50.7 |
| Contract governance | 0.0 |
| Operational transparency | 10.5 |
| Developer ergonomics | 19.0 |
| Access clarity | 5.3 |

**Agent readiness 16.6** — agent-aware

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | — |
| Idempotency | — |
| Error Semantics | — |
| OpenAPI Examples | documented (partial credit) |
| Rate Limit Signal | derived (partial credit) |
| Event Surface Described | — |
| Agent Skills | — |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |

**Regulatory alignment 5.9** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/farcaster/](https://apis.io/providers/farcaster/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Farcaster: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/farcaster/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
