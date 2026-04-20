---
tags: [status/stable]
related: [[Create_Short_Url_Flow]], [[User_Personas]]
author: phinhd
---
# Business Rules

Core logic rules that govern the URL Shortener behavior.

## URL Creation

1. **Absolute URL Required**: The system only accepts absolute URLs (e.g., must start with `http://` or `https://`).
2. **Anonymous Restrictions**: Users who are not logged in cannot request custom aliases. They receive a randomly generated 6-8 character code.
3. **Alias Uniqueness**: Custom aliases must be unique across the entire system.
4. **Alias Normalization**: All aliases and codes are converted to lowercase or a normalized case-insensitive format to prevent confusion.
5. **Default Expiration**: Short URLs expire after 30 days by default if not specified (configurable in app settings).

## Security & Auth

1. **Email Verification**: Users must verify their email before they can fully manage links.
2. **Rate Limiting**: (Planned) Anonymous creation is limited to 5 requests per IP per hour.
3. **Password Security**: Passwords must be at least 8 characters and are hashed using BCrypt.
4. **Token Expiration**:
    - Access Token: 1 hour.
    - Refresh Token: 7 days.
    - Password Reset: 15 minutes.

## Resolution & Analytics

1. **Active Only**: A short URL must be `is_active = true` and `expires_at > Now` to resolve.
2. **Atomic Clicks**: Every resolution attempt (except 404s) results in exactly one `Click_Event` entry.
3. **Country Detection**: If the request headers contain a country code (e.g., from Cloudflare), it MUST be recorded.
