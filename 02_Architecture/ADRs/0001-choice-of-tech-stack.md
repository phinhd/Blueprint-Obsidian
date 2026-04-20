---
tags: [status/stable, layer/infrastructure]
related: [[Tech_Stack]]
author: phinhd
---
# ADR 0001: Choice of Tech Stack

## Status
Accepted

## Context
We need a robust, scalable foundations for a URL Shortener service that supports high-concurrency redirection and secure user management.

## Decisions

### 1. Backend: ASP.NET Core 8
- **Why**: Excellent performance, native support for JWT, EF Core, and high-quality dependency injection.
- **Consequences**: Strong type safety, better maintenance for long-term project.

### 2. Frontend: Angular 17+
- **Why**: Standardized structure, built-in routing, and state management suitable for an administrative dashboard.
- **Consequences**: Steeper learning curve but consistent architectural patterns.

### 3. Database: PostgreSQL
- **Why**: Open-source, supports JSONB for flexible logging, and has robust transactional support.
- **Consequences**: Reliable persistence for user and URL data.

### 4. Cache: Redis
- **Why**: Extremely fast lookups for hot short codes.
- **Consequences**: Adds an infrastructure dependency but significantly reduces database load during spikes.

## Consequences
- The system will be able to handle thousands of requests per second for redirection.
- Developers will need familiarity with C# and TypeScript.
