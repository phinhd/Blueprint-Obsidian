---
tags: [status/stable, layer/application]
related: [[Authenticate_ERD]], [[User]], [[Refresh_Token]]
author: phinhd
---
# Authenticate Workflow

## Goal

Provide secure login with refresh tokens, roles, and verification flows.

## Flow (High Level)

```mermaid
sequenceDiagram
    participant User
    participant API
    participant DB
    
    User->>API: POST /api/auth/login (credentials)
    API->>DB: Check User credentials & lockout
    alt Success
        API->>DB: Store RefreshToken
        API-->>User: returns accessToken + refreshToken
    else Requires Verification
        API->>DB: Create IdentityVerification token
        API-->>User: 403 Forbidden (Verify Email)
    else Failed
        API-->>User: 401 Unauthorized
    end
```

## Details

- **Scope**: Local login, role assignment, email/OTP verification, email tracking.
- **Roles**: Loaded via [[User_Role]] for authorization checks.
- **Logout**: Revokes refresh tokens in [[Refresh_Token]].

## ERD Reference

See [[Authenticate_ERD]].
