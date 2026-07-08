# Day 7 — Terraform CLI

**Date:** Jul 6, 2026 | **Mod #5** | **Est. time:** 50 min

## Lessons Covered
- Intro to CLI
- CLI Demo
- Making the Most of CLI + Demo
- Quiz

## Notes

### Intro to CLI
- The Terraform CLI is the primary interface for the workflow: `init`, `plan`, `apply`, `destroy`, `validate`, and more.
- Check installed version: `terraform version`.

### CLI Demo
- Practical usage of core commands in a terminal.
- Common flags: `-auto-approve`, `-out`, `-var`, `-var-file`, `-target`.

### Making the Most of the CLI
- `terraform fmt` — auto-formats HCL files to canonical style.
- `terraform show` — inspect current state or a saved plan.
- `terraform graph` — output the resource dependency graph (e.g., for visualization).
- Using `-out` with `plan` saves a plan file that `apply` can execute exactly, avoiding drift between plan and apply.

## Key Takeaways
- Efficient CLI usage (flags, formatting, plan files) reduces mistakes and speeds up daily workflow.
