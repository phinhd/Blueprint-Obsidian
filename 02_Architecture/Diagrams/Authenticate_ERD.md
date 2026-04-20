---
tags: [status/stable, layer/infrastructure]
related: [[User]], [[Refresh_Token]], [[Identity_Verification]], [[Role]], [[User_Role]], [[Email_Log]]
author: phinhd
---
# Authenticate ERD

## Scope

Entities involved in authentication, authorization, and verification.

```mermaid
erDiagram
    USER ||--o{ REFRESH_TOKEN : owns
    USER ||--o{ IDENTITY_VERIFICATION : verifies
    USER ||--o{ USER_ROLE : has
    ROLE ||--o{ USER_ROLE : includes
    USER ||--o{ EMAIL_LOG : receives

    USER {
        int user_id PK
        string email
        string name
        string password_hash
        boolean is_verified
        boolean two_factor_enabled
        datetime lockout_end
        datetime created_at
        datetime updated_at
        datetime deleted_at
    }

    REFRESH_TOKEN {
        int id PK
        string token
        int user_id FK
        datetime expires_at
        datetime created_at
        boolean is_revoked
    }

    ROLE {
        int role_id PK
        string name
    }

    USER_ROLE {
        int user_id FK
        int role_id FK
    }

    IDENTITY_VERIFICATION {
        int id PK
        int user_id FK
        string type
        string token
        datetime expires_at
        boolean is_used
    }

    EMAIL_LOG {
        string id PK
        string recipient
        string subject
        string body
        datetime sent_at
        string status
        string error_message
        int user_id FK
    }
```

## Notes

- REFRESH_TOKEN.id can be Guid or int depending on implementation.
- IDENTITY_VERIFICATION.type values include Email_Confirmation and Password_Reset.
- USER_ROLE is a many-to-many join between USER and ROLE.
- EMAIL_LOG.user_id is nullable for guest recipients.
