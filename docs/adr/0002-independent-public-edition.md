# ADR-0002: Independent Public Edition

## Status

Accepted — 2026-10-28

## Context

This repository is derived from an earlier private standard. It needs a public
home with personal ownership and an independent maintenance lifecycle.

## Decision

Publish a fresh-history, independently maintained edition owned personally by
Jacques Thomazo, under the MIT license. Keep the same rule set as standard
version 2, including its rule identifiers, semantics, and major version.

The public home is `https://github.com/JayTeeBat/repo-standard-kit`.

## Consequences

- Release history starts with this edition's first public release, `v2.0.0`.
- Install instructions use HTTPS and this edition's release tag.
- This repository's compliance workflow checks its local checkout, so it needs
  no self-referencing commit SHA.
- After publication, consumers choosing the reusable workflow must resolve
  this edition's `v2.0.0` tag to its full commit SHA and replace `<full-sha>` in
  the documented example. Third-party action pins remain unchanged.
- Future maintenance and releases are independent of the earlier standard.
