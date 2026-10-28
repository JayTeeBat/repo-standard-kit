# ADR-0001: Enforcement Requires A Paid GitHub Plan

## Status

Accepted — 2026-08-18

## Context

A workflow that runs on every pull request still permits a merge when it fails
unless branch protection or rulesets require its status checks.

On GitHub Free, branch protection and rulesets for private repositories can
return `403` even when the caller has administrative permissions. This is a
plan limitation rather than a token-permissions problem. Private repositories
need a plan that supports required status checks to enforce the standard.

## Decision

State enforcement support as an explicit precondition rather than weakening
the requirement.

`docs/quality-gates.md` §10 documents the required protection on `main`.
Enforcement is not softened to "where supported": that would allow repositories
to claim alignment while leaving the gates advisory.

## Consequences

- A private repository without the required plan can run the gates, but cannot
  claim full alignment while its enforcement remains advisory.
- Gate failures must block merges for a repository to satisfy the standard.
- Public repositories can use branch protection without a paid plan.
- The settings and verification commands remain documented in the quality gates.

## Revisit When

GitHub changes enforcement availability, or the standard explicitly changes its
requirement that gate failures block merges.
