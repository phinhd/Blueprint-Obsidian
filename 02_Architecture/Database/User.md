---
tags: [status/stable, layer/infrastructure]
related: [[Role]], [[User_Role]], [[Refresh_Token]]
author: phinhd
---
# Table: User

## Columns

| Name | Type | Notes |
| --- | --- | --- |
| user_id | int | Primary key. |
| email | string | Unique user email. |
| name | string | Display name. |
| password_hash | string | Password hash. |
| is_verified | boolean | Email verified flag. |
| two_factor_enabled | boolean | 2FA enabled flag. |
| lockout_end | datetime | Lockout end timestamp. |
| created_at | datetime | Created timestamp. |
| updated_at | datetime | Updated timestamp. |
| deleted_at | datetime | Soft delete timestamp. |
