---
tags: [status/stable]
related: [[Project_Index]]
author: phinhd
---
# Handoff Summary (2026-04-17)

## Scope Completed

- Created English wiki structure under url-shorten-wiki with quick links, per-use-case docs, and ERD index.
- Split ERD by use case and added Mermaid diagrams per flow.
- Added Authenticate use case + ERD including RefreshToken, Role/UserRole, IdentityVerification, and EmailLog.
- Added Reset Password (Token) use case + ERD with frontend validation flow and backend security steps.
- Added database table catalog under url-shorten-wiki/databases with consistent table specs.
- Moved hardcoded expiration dates for JWT access/refresh tokens and password reset tokens to application settings.
- Implemented robust URL normalization and host validation (handling missing schemes, ports, and TLDs).

## Migration Note (2026-04-20)

The wiki was reorganized into the **00-05 structure** to optimize for Obsidian and AI context retrieval.

## Pending Implementation (Code)

- Backend: updated Auth handlers to use configurable expiration settings.
- Frontend: implement reset-password page logic (token check, form state, call backend).
- Tests: add unit/integration tests for reset flow.
