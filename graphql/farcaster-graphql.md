---
title: Farcaster GraphQL Schema
description: >-
  GraphQL projection of the Farcaster Snapchain protobuf data model,
  covering the Hub message types, social graph, on-chain events, and
  the HubService RPC surface.
---

# Farcaster GraphQL Schema

## Overview

Farcaster's canonical wire format is **protobuf over gRPC** (the HubService
defined in the Snapchain repository) plus a JSON/REST gateway. There is no
first-party GraphQL endpoint, but several third-party indexers expose GraphQL
interfaces over the same underlying data model.

The schema in `farcaster-schema.graphql` is a faithful SDL projection of the
Snapchain protobuf definitions. It can be used:

- as a GraphQL gateway schema (backed by a Hub or Neynar REST calls),
- as a documentation artefact describing every Farcaster data type, or
- as a starting point for a custom GraphQL layer over the Hub HTTP API.

## Source Protobuf Definitions

| Proto file | Location |
|---|---|
| `message.proto` | `farcasterxyz/snapchain/proto/definitions/message.proto` |
| `hub_event.proto` | `farcasterxyz/snapchain/proto/definitions/hub_event.proto` |
| `onchain_event.proto` | `farcasterxyz/snapchain/proto/definitions/onchain_event.proto` |
| `username_proof.proto` | `farcasterxyz/snapchain/proto/definitions/username_proof.proto` |
| `rpc.proto` (HubService) | `farcasterxyz/snapchain/proto/definitions/rpc.proto` |

Reference: https://github.com/farcasterxyz/snapchain/tree/main/proto/definitions

## Core Types

### Message Envelope

Every delta operation on Farcaster is wrapped in a `Message` envelope containing:

- `hash` — Blake3 digest of the `MessageData` payload
- `hashScheme` — always `HASH_SCHEME_BLAKE3` today
- `signature` / `signatureScheme` — Ed25519 (app key) or EIP-712 (custody key)
- `signer` — the public key or address that signed the message
- `data` — a `MessageData` object with the actual payload

### MessageData

`MessageData` carries:

- `type` (`MessageType`) — discriminates the body union
- `fid` — the Farcaster ID of the author
- `timestamp` — seconds since the Farcaster epoch (2021-01-01T00:00:00Z)
- `network` — mainnet / testnet / devnet
- one body field matching the `type` value

### Body Types

| MessageType | Body type | Description |
|---|---|---|
| `MESSAGE_TYPE_CAST_ADD` | `CastAddBody` | Publish a new cast |
| `MESSAGE_TYPE_CAST_REMOVE` | `CastRemoveBody` | Delete a cast by hash |
| `MESSAGE_TYPE_REACTION_ADD` | `ReactionBody` | Like or recast a cast or URL |
| `MESSAGE_TYPE_REACTION_REMOVE` | `ReactionBody` | Remove a reaction |
| `MESSAGE_TYPE_LINK_ADD` | `LinkBody` | Follow (or other link type) another FID |
| `MESSAGE_TYPE_LINK_REMOVE` | `LinkBody` | Unfollow |
| `MESSAGE_TYPE_LINK_COMPACT_STATE` | `LinkCompactStateBody` | Compacted full follow list |
| `MESSAGE_TYPE_VERIFICATION_ADD_ETH_ADDRESS` | `VerificationAddAddressBody` | Prove address ownership |
| `MESSAGE_TYPE_VERIFICATION_REMOVE` | `VerificationRemoveBody` | Remove a verification |
| `MESSAGE_TYPE_USER_DATA_ADD` | `UserDataBody` | Set a profile field |
| `MESSAGE_TYPE_USERNAME_PROOF` | `UserNameProof` | Claim a fname / ENS / Basename |
| `MESSAGE_TYPE_FRAME_ACTION` | `FrameActionBody` | Frame (Mini App) button press |
| `MESSAGE_TYPE_LEND_STORAGE` | `LendStorageBody` | Lend storage units to another FID |
| `MESSAGE_TYPE_KEY_ADD` | `KeyAddBody` | Register a gasless Ed25519 signer key |
| `MESSAGE_TYPE_KEY_REMOVE` | `KeyRemoveBody` | Revoke an Ed25519 signer key |

### Social Graph (Higher-Level Types)

The schema also defines composite read-model types that aggregate raw messages:

| Type | Description |
|---|---|
| `FarcasterUser` | Resolved profile from all `UserDataBody` messages for a FID |
| `Cast` | Cast with resolved author, engagement counts, and replies |
| `Reaction` | Reaction with resolved author and target cast |
| `Link` | Follow/unfollow with resolved `from` and `to` profiles |
| `Channel` | Parent URL namespace (e.g. `/dev`, `/founders`) |
| `Frame` | Mini App interaction surface embedded in a cast |
| `StorageUnit` | Per-FID storage allocation with generation and expiry |

### On-Chain Events

Farcaster contracts on Optimism emit four event categories tracked in
`OnChainEvent`:

| OnChainEventType | Description |
|---|---|
| `EVENT_TYPE_SIGNER` | Ed25519 app key add / remove on the Key Registry |
| `EVENT_TYPE_SIGNER_MIGRATED` | Signer set migration |
| `EVENT_TYPE_ID_REGISTER` | FID registration, transfer, or recovery change |
| `EVENT_TYPE_STORAGE_RENT` | Storage units purchased |
| `EVENT_TYPE_TIER_PURCHASE` | Pro tier subscription purchased |

### Hub Events (Stream)

`HubEvent` is the real-time event emitted by a Snapchain node. Event types:

| HubEventType | Meaning |
|---|---|
| `HUB_EVENT_TYPE_MERGE_MESSAGE` | A message was accepted into the store |
| `HUB_EVENT_TYPE_PRUNE_MESSAGE` | A message was pruned (storage limit) |
| `HUB_EVENT_TYPE_REVOKE_MESSAGE` | A message was revoked (signer removed) |
| `HUB_EVENT_TYPE_MERGE_USERNAME_PROOF` | A username proof was merged |
| `HUB_EVENT_TYPE_MERGE_ON_CHAIN_EVENT` | An on-chain event was merged |
| `HUB_EVENT_TYPE_MERGE_FAILURE` | A merge was rejected |
| `HUB_EVENT_TYPE_BLOCK_CONFIRMED` | A Snapchain block was finalised |

## Query Examples

### Fetch a User Profile

```graphql
query GetUser($fid: UInt64!) {
  farcasterUser(fid: $fid) {
    fid
    username
    displayName
    bio
    pfpUrl
    primaryAddressEthereum
    verifications {
      data {
        verificationAddAddressBody {
          address
          protocol
        }
      }
    }
  }
}
```

### Fetch Casts by FID

```graphql
query GetCasts($fid: UInt64!) {
  castsByFid(fid: $fid, pageSize: 20) {
    hash
    data {
      timestamp
      castAddBody {
        text
        embeds { url castId { fid hash } }
        parentUrl
      }
    }
  }
}
```

### Fetch Replies to a Cast

```graphql
query GetReplies($parentFid: UInt64!, $parentHash: Bytes!) {
  castsByParent(parentFid: $parentFid, parentHash: $parentHash) {
    hash
    data {
      fid
      castAddBody { text }
    }
  }
}
```

### Fetch Followers of an FID

```graphql
query GetFollowers($fid: UInt64!) {
  linksByTarget(targetFid: $fid, linkType: "follow") {
    data {
      fid
      linkBody { type displayTimestamp }
    }
  }
}
```

### Subscribe to Hub Events

```graphql
subscription WatchFeed {
  hubEvents(eventTypes: [HUB_EVENT_TYPE_MERGE_MESSAGE]) {
    id
    type
    blockNumber
    mergeMessageBody {
      message {
        data {
          fid
          type
          castAddBody { text }
          reactionBody { type targetCastId { fid hash } }
        }
      }
    }
  }
}
```

### Submit a Signed Message

```graphql
mutation Publish($bytes: Bytes!) {
  submitMessage(messageBytes: $bytes) {
    hash
    data { type fid timestamp }
  }
}
```

## Third-Party GraphQL Gateways

| Provider | Endpoint | Notes |
|---|---|---|
| Airstack | `https://api.airstack.xyz/gql` | Requires API key; covers Farcaster social data and cross-chain identity |
| Neynar | `https://api.neynar.com/` | REST-first but wraps the same Hub data model |

## References

- Snapchain Hub API reference: https://snapchain.farcaster.xyz/reference
- Farcaster protocol docs: https://docs.farcaster.xyz/
- hub-monorepo (TypeScript SDK): https://github.com/farcasterxyz/hub-monorepo
- snapchain (Rust implementation): https://github.com/farcasterxyz/snapchain
- Neynar API: https://docs.neynar.com/reference
