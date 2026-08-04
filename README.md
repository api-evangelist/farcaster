# Farcaster (farcaster)

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

Farcaster is a decentralised social protocol built on Snapchain, an append-only state machine that stores casts, reactions, follows, and user profile data. The protocol publishes a Hub / Snapchain reference implementation, the Mini Apps SDK (formerly Frames) for distributing interactive apps inside Farcaster feeds, Sign In with Farcaster (SIWF) for authentication, and AuthKit for React-based sign-in. The Warpcast client (now rebranded Farcaster app at farcaster.xyz) is the primary consumer surface. Indexer providers such as Neynar host scaled Hub APIs and value-added read / write / webhook APIs at api.neynar.com.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/farcaster/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/farcaster/refs/heads/main/apis.yml)

## Scope

- **Type:** Index
- **Position:** Producer
- **Access:** 3rd-Party

## Tags

- Social
- Decentralized
- Protocol
- Mini Apps
- Frames
- Authentication
- Web3
- SDKs

## Timestamps

- **Created:** 2026-05-23
- **Modified:** 2026-05-23

## APIs

### Snapchain / Hub API

Query interface for Farcaster's Snapchain network - read casts, reactions, follows, user data, and verifications by FID; submit signed messages; and run a Snapchain node for full replication. Public reference endpoint is hosted at snapchain.farcaster.xyz.

- **Human URL:** [https://snapchain.farcaster.xyz/](https://snapchain.farcaster.xyz/)
- **Base URL:** `https://snapchain.farcaster.xyz`

#### Tags

- Snapchain
- Hub API
- Reads
- Writes

#### Properties

- [Documentation](https://snapchain.farcaster.xyz/)
- [Reference](https://snapchain.farcaster.xyz/reference)
- [Run a  Node](https://snapchain.farcaster.xyz/guides/running-a-node)
- [Postman Collection](collections/farcaster.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/farcaster.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Farcaster Mini Apps SDK

JavaScript SDK for building Mini Apps (the evolution of Frames) that run inside Farcaster feeds and clients. Provides host bridge, context, wallet actions, notifications, and analytics for permissionlessly distributed social apps.

- **Human URL:** [https://miniapps.farcaster.xyz/](https://miniapps.farcaster.xyz/)
- **Base URL:** `https://miniapps.farcaster.xyz/`

#### Tags

- Mini Apps
- Frames
- SDK
- Social

#### Properties

- [Documentation](https://miniapps.farcaster.xyz/)
- [Postman Collection](collections/farcaster.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/farcaster.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Sign In with Farcaster (SIWF)

Authentication flow that lets users sign in to third-party apps with their Farcaster identity, returning a verified FID and optional profile data. Backed by EIP-4361-style signed messages.

- **Human URL:** [https://docs.farcaster.xyz/developers/siwf](https://docs.farcaster.xyz/developers/siwf)
- **Base URL:** `https://docs.farcaster.xyz/developers/siwf`

#### Tags

- Authentication
- SIWF
- Identity

#### Properties

- [Documentation](https://docs.farcaster.xyz/developers/siwf)
- [Postman Collection](collections/farcaster.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/farcaster.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Farcaster AuthKit (React)

React toolkit wrapping Sign In with Farcaster - provides hooks and components for the QR-code / deep-link handoff to a Farcaster client and returns the verified user context to the host app.

- **Human URL:** [https://docs.farcaster.xyz/auth-kit/installation](https://docs.farcaster.xyz/auth-kit/installation)
- **Base URL:** `https://docs.farcaster.xyz/auth-kit/installation`

#### Tags

- SDK
- React
- Authentication

#### Properties

- [Documentation](https://docs.farcaster.xyz/auth-kit/installation)
- [Examples](https://docs.farcaster.xyz/auth-kit/examples)
- [Postman Collection](collections/farcaster.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/farcaster.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Neynar Hosted Farcaster API

Third-party indexer providing hosted Hub access, indexed read APIs (users, casts, channels, feeds), write APIs (publish casts, reactions, follows), webhooks for real-time events, a Node.js SDK, and a Mini Apps framework with analytics. Most widely used scaled gateway to Farcaster data.

- **Human URL:** [https://docs.neynar.com/](https://docs.neynar.com/)
- **Base URL:** `https://api.neynar.com`

#### Tags

- Neynar
- Indexer
- Hosted Hub
- Webhooks

#### Properties

- [Documentation](https://docs.neynar.com/)
- [Reference](https://docs.neynar.com/reference)
- [Postman Collection](collections/farcaster.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/farcaster.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Warpcast / Farcaster Client API

Client-side API exposed by the Warpcast / Farcaster app for client-specific surfaces (channels, mentions, direct casts, mini-app contexts) layered above the Snapchain protocol APIs.

- **Human URL:** [https://docs.farcaster.xyz/reference/warpcast/api](https://docs.farcaster.xyz/reference/warpcast/api)
- **Base URL:** `https://api.warpcast.com`

#### Tags

- Warpcast
- Client API
- Channels

#### Properties

- [Documentation](https://docs.farcaster.xyz/reference/warpcast/api)
- [Postman Collection](collections/farcaster.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/farcaster.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Website](https://www.farcaster.xyz/)
- [Documentation](https://docs.farcaster.xyz/)
- [Mini  Apps](https://miniapps.farcaster.xyz/)
- [Snapchain](https://snapchain.farcaster.xyz/)
- [Git Hub](https://github.com/farcasterxyz)
- [Neynar](https://neynar.com/)

## Maintainers

**FN:** API Evangelist
**URL:** https://apievangelist.com
