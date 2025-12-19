# ADR-002: Use SQLite as the Local Database

## Status
Accepted

## Context
The application must run fully offline, persist data locally, and support straightforward backup/restore. The database must be embedded and require no server setup.

Alternatives considered:
- Local file storage (JSON)
- SQL Server LocalDB
- LiteDB / other embedded databases

## Decision
Use **SQLite** as the local database.

## Consequences
### Positive
- Proven embedded database with good performance and reliability.
- Simple deployment (single file) and easy backup/restore.
- SQL querying enables reporting and advanced filtering.

### Negative / Trade-offs
- Concurrency is limited compared to client-server DBs (acceptable for single-user v1).
- Requires clear migrations strategy for schema evolution.
