---
tags: [status/stable, layer/application]
related: [[Reset_Password_ERD]], [[Identity_Verification]]
author: phinhd
---
# Reset Password Workflow

## Goal

Allow users to reset their password using a time-limited token.

## Process Flow

```mermaid
graph TD
    A[User clicks link in email] --> B[Frontend reads Token]
    B --> C[GET /api/auth/verify-token]
    C --> D{Token Valid & Not Expired?}
    D -- No --> E[Show Error / Request New Link]
    D -- Yes --> F[Display Reset Form]
    F --> G[User Submits New Password]
    G --> H[POST /api/auth/reset-password]
    H --> I[Update User Password_Hash]
    I --> J[Mark Token as Used]
    J --> K[200 Success]
```

## Security

- Use a short expiration window (15-30 minutes).
- `is_used` prevents replay attacks.
- Passwords are hashed with BCrypt.

## ERD Reference

See [[Reset_Password_ERD]].
