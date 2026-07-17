# Day 14 — Terraform State II (004 focus)

**Date:** Jul 13, 2026 | **Mod #8** | **Est. time:** 45 min

## Lessons Covered
- Migrate State Demo
- Inspecting State + Demo
- State Drift Walkthrough
- Lose State Walkthrough
- Refresh-Only Mode + Demo

## Notes

### Migrate State Demo
- When you add or change a `backend` block, `terraform init` detects the change and prompts to migrate existing state (local → remote, or between backends).
- Terraform copies the state content to the new backend location; the old local `.tfstate` is typically left behind and should be cleaned up/gitignored once migration is confirmed.

### Inspecting State
- `terraform show` — human-readable dump of the current state.
- `terraform state list` — lists all resources tracked in state.
- `terraform state show <resource>` — detailed attributes for a single tracked resource.
- Useful for auditing what Terraform actually thinks exists, especially when debugging drift.

### State Drift Walkthrough
- **Drift** = real infrastructure has changed outside of Terraform (manual console edit, another tool, etc.), so it no longer matches state/config.
- `terraform plan` surfaces drift by comparing refreshed real-world data against state and config.
- Resolution: either update your `.tf` config to match the new reality (if the change should stick), or `apply` to revert it back to the declared state.

### Lose State Walkthrough
- If a state file is lost (deleted, corrupted, never backed up) Terraform has no record of what it manages — it would try to recreate everything from scratch on the next `apply`, potentially causing duplicate resources or errors (e.g., name conflicts).
- Recovery options: restore from a backend's versioning (e.g., S3 bucket versioning), or manually `terraform import` each real resource back into a fresh state file.
- This is the strongest practical argument for remote state with versioning enabled — local state has no built-in recovery path.

### Refresh-Only Mode
- `terraform plan -refresh-only` (or `apply -refresh-only`) updates state to match real infrastructure **without** proposing any config changes — it only reconciles state, doesn't create/modify/destroy resources.
- Useful when you know drift occurred and want state to reflect reality first, before deciding whether to also update your `.tf` config.

## Key Takeaways
- State inspection commands (`show`, `state list`, `state show`) are your primary debugging toolkit when something doesn't match expectations.
- Losing state is a serious operational risk — remote state + versioning is the mitigation, not just a "nice to have."
- Refresh-only mode separates "sync state to reality" from "change infrastructure to match config" — two different problems, two different fixes.
