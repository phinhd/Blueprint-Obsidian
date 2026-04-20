---
tags: [status/stable, layer/infrastructure]
related: [[User]], [[Short_Url]], [[Click_Event]], [[Authenticate_ERD]]
author: phinhd
---
# Database Schema

This document provides a high-level overview of the database structure for the URL Shortener project. For detailed column definitions, refer to the individual table notes.

## Core Entities

- [[User]]: User accounts and authentication data.
- [[Short_Url]]: The core mapping between short codes and original URLs.
- [[Click_Event]]: Tracking data for each time a short URL is resolved.

## Authentication & Security

- [[Role]]: User roles (Admin, User, etc.).
- [[User_Role]]: Mapping users to roles.
- [[Refresh_Token]]: JWT refresh tokens for persistence.
- [[Identity_Verification]]: Tokens for email confirmation and password reset.

## Logs & Supporting Tables

- [[Email_Log]]: History of outgoing emails.
- [[Custom_Alias_Reservation]]: Reserved aliases to prevent collisions.

## Visual Diagrams

- [[Authenticate_ERD]]: Auth and Identity relationships.
- [[Create_Short_Url_ERD]]: URL ownership.
- [[Resolve_Short_Url_ERD]]: Click tracking logic.
- [[Url_Analytics_ERD]]: Data aggregation for statistics.
