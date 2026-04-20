---
tags: [status/stable]
related: [[Business_Rules]]
author: phinhd
---
# User Personas

Defining the key users of the URL Shortener project.

## 1. Guest (Anonymous User)
- **Goal**: Quickly shorten a URL without creating an account.
- **Pain Point**: Cannot track analytics or manage long-term links.
- **Capabilities**:
    - Create short URLs (auto-generated code only).
    - Resolve short URLs.

## 2. Registered User
- **Goal**: Manage a collection of short links and view detailed analytics.
- **Pain Point**: Needs a custom brand alias for business marketing.
- **Capabilities**:
    - All Guest capabilities.
    - Create short URLs with **Custom Aliases**.
    - View click stats (referrer, country, timeline).
    - Manage active/inactive status of links.

## 3. Administrator
- **Goal**: Monitor system health and manage abuse.
- **Capabilities**:
    - View all system-wide links and users.
    - Revoke/Delete malicious short codes.
    - Access system logs (Email, Errors).
