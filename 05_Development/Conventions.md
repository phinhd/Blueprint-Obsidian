---
tags: [status/stable, layer/infrastructure]
related: [[Database_Schema]]
author: phinhd
---
# Database Conventions

## Common Fields

| Name | Type | Notes |
| --- | --- | --- |
| created_at | datetime | Audit timestamp. |
| updated_at | datetime | Audit timestamp. |
| deleted_at | datetime | Soft delete timestamp. |

## Notes

- Not every table uses all three audit fields.
- Nullable fields should be documented per table.
- Use snake_case for column names.
- Primary keys are typically named `{table_name}_id` or just `id`.
