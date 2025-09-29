# ADR-0001: Choose PostgreSQL as the Primary Data Store

- **Status**: Accepted
- **Date**: 2025-09-29
- **Context**: We need a transactional store with strong consistency, SQL, migrations, and good local dev ergonomics.
- **Decision**: Use PostgreSQL 15 for production. Use SQLite for local development and tests where concurrency is low.
- **Consequences**:
  - ✅ Mature ecosystem (migrations, ORMs, extensions).
  - ✅ Easy to run locally via containers or a cloud service.
  - ⚠️ Requires managed backups and monitoring in production.
- **Alternatives considered**:
  - MySQL: similar fit; team expertise is lower.
  - MongoDB: weaker transactional guarantees for our needs.
- **Follow‑ups**:
  - Provision managed Postgres with automated backups.
  - Add health checks, connection pooling, and migration gating in CI.
