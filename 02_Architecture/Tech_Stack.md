---
tags: [status/stable]
related: [[0001-choice-of-tech-stack]]
author: phinhd
---
# Tech Stack

The current platform versions and libraries used in the project.

## Backend
- **Framework**: .NET 8 (ASP.NET Core)
- **Language**: C# 12
- **ORM**: Entity Framework Core 8
- **Database**: PostgreSQL
- **Security**: JWT (System.IdentityModel.Tokens.Jwt), BCrypt for password hashing.
- **Communication**: Resend API (for emails).

## Frontend
- **Framework**: Angular 17.x
- **Language**: TypeScript 5.x
- **UI Architecture**: Component-based with standalone components.
- **Styling**: Vanilla CSS / SCSS.

## Infrastructure
- **Hosting**: Appwrite (Planned/Current)
- **Proxy**: Cloudflare (Optional)
