# Day 13 — Terraform State I

**Date:** Jul 12, 2026 | **Mod #8** | **Est. time:** 30 min

## Lessons Covered
- Intro to State
- Where to Store State
- Remote State Config + Demo

## Notes

### Intro to State
- Terraform state (`terraform.tfstate`) is a JSON file mapping your configuration to real-world resources.
- It's how Terraform knows what it's already created, tracks resource metadata/attributes, and computes the diff during `plan`.
- Without state, Terraform would have no way to know whether a resource already exists or needs to be created.

### Where to Store State
- **Local state** (default): a `.tfstate` file on disk. Fine for solo experimentation, risky for teams — no locking, no shared visibility, easy to lose or overwrite.
- **Remote state**: stored in a backend (S3, Terraform Cloud, Azure Storage, GCS, etc.), shared across the team, supports locking to prevent concurrent
