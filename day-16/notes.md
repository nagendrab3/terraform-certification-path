# Day 16 — Reusable Code II

**Date:** Jul 16, 2026 | **Mod #9** | **Est. time:** 30 min

## Lessons Covered
- Locals + Lab
- count Meta-Argument + Lab

## Notes

### Locals
- Declared in a `locals` block — named values computed from expressions, used to avoid repeating the same logic/value throughout a configuration.
```hcl
  locals {
    environment_tag = "${var.environment}-${var.project_name}"
  }
```
- Referenced as `local.environment_tag` (note: `local.`, singular, unlike `var.`).
- Difference from variables: locals are **not** set by the caller (no CLI flag, no `.tfvars`) — they're computed internally from
