# ADR-003: Offline-First System Design

## Status
Accepted

## Context
The workshop must be able to operate without internet access. The system must not depend on external services for core operations (work orders, stock, payments, printing).

Future requirement: optional mobile support and synchronization, without forcing cloud dependencies in v1.

## Decision
Adopt an **offline-first** design:
- Local persistence is the source of truth in v1.
- No mandatory external API for core features.
- Keep the model compatible with future sync (UUIDs, audit fields, soft deletes).

## Consequences
### Positive
- The system works reliably in any connectivity scenario.
- Faster operations and fewer runtime failures.
- Easier deployment for small businesses.

### Negative / Trade-offs
- Future sync requires careful conflict and change tracking (planned, not implemented in v1).
- Some “cloud” conveniences (shared access, multi-device) are not available in v1 by design.
