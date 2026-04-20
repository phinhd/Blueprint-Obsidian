---
tags: [status/stable, layer/api]
related: [[Authenticate_Flow]], [[User]]
author: phinhd
---
# Auth API

Handles login, session persistence, and identity verification.

## Login

- **Endpoint**: `POST /api/auth/login`
- **Auth**: None (Public)

### Request Body
```json
{
  "email": "phiho@example.com",
  "password": "SecurePassword123!"
}
```

### Response (200 OK)
```json
{
  "accessToken": "eyJh... (valid for 1h)",
  "refreshToken": "abcdef123456... (valid for 7d)",
  "user": {
    "id": 1,
    "email": "phiho@example.com",
    "name": "Phi Ho"
  }
}
```

---

## Refresh Token

- **Endpoint**: `POST /api/auth/refresh`
- **Auth**: None (Uses RefreshToken)

### Request Body
```json
{
  "refreshToken": "abcdef123456..."
}
```

### Response (200 OK)
Returns a new `accessToken` and `refreshToken`.

---

## Request Password Reset

- **Endpoint**: `POST /api/auth/forgot-password`

### Request Body
```json
{
  "email": "phiho@example.com"
}
```

### Response (200 OK)
An email is sent with a reset link containing a token.
