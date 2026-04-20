---
tags: [status/draft]
related: [[Tech_Stack]]
author: phinhd
---
# Setup Guide

This guide outlines the steps to set up the URL Shortener project locally.

## Prerequisites

- .NET 8 SDK
- Node.js (v20+)
- PostgreSQL
- Redis (Optional, for caching)

## Backend Setup (ASP.NET Core)

1. Navigate to `aspnet-core/src/UrlShortener.HttpApi`.
2. Update `appsettings.json` with your PostgreSQL connection string.
3. Run migrations:
   ```bash
   dotnet ef database update
   ```
4. Start the API:
   ```bash
   dotnet run
   ```

## Frontend Setup (Angular)

1. Navigate to `angular/`.
2. Install dependencies:
   ```bash
   npm install
   ```
3. Start the dev server:
   ```bash
   npm start
   ```
4. Open `http://localhost:4200` in your browser.

## Troubleshooting

- Check `Email_Log` in the database if verification emails are not appearing (the project uses Resend or a mock service).
- Ensure PostgreSQL is running and the user has permissions to create databases.
