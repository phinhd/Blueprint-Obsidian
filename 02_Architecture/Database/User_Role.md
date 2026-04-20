---
tags: [status/stable, layer/infrastructure]
related: [[User]], [[Role]]
author: phinhd
---
# Table: UserRole

## Columns

| Name | Type | Notes |
| --- | --- | --- |
| user_id | int | Foreign key to User. |
| role_id | int | Foreign key to Role. |

## Notes

- Many-to-many join between User and Role.
