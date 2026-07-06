# Day 5 — Core Terraform Workflow I

**Date:** Jul 4, 2026 | **Mod #4** | **Est. time:** 30 min

## Lessons Covered
- Workflow Intro
- Terraform Init
- Terraform Plan

## Notes

### Core Workflow Order
```
terraform init → terraform plan → terraform apply
```

### `terraform init`
- Initializes a working directory.
- Downloads required provider plugins.
- Sets up the backend for state storage.
- Initializes any referenced modules.
- Does **not** touch real infrastructure.

### `terraform plan`
- Shows an execution plan: what will be created, changed, or destroyed.
- Compares current state against desired configuration.
- Does **not** apply any changes — read-only/preview step.
- Lets you (or a reviewer) catch mistakes before anything real happens.

## Key Takeaways
- `plan` before `apply` is a safety habit — share plan output for review before approving changes, especially in production.
