# Day 6 — Core Terraform Workflow II

**Date:** Jul 5, 2026 | **Mod #4** | **Est. time:** 45 min

## Lessons Covered
- Resource Graph
- Terraform Apply
- Terraform Destroy
- Terraform Validate
- Quiz

## Notes

### Resource Graph
- Terraform builds a dependency graph of all resources, data sources, and modules.
- Used to determine safe execution order for both `apply` and `destroy`.
- Resources with no dependency on each other may be created/destroyed in parallel.
- Circular dependencies (A needs B, B needs A) generally cannot be resolved and will error.

### `terraform apply`
- Executes the plan and makes real changes to infrastructure.
- Prompts for confirmation unless `-auto-approve` is used.
- If it fails partway through, successfully created resources are recorded in state — they are not automatically rolled back.

### `terraform destroy`
- Removes all resources managed by the configuration.
- A deliberately separate, explicit command — destructive/irreversible actions shouldn't be easy to trigger by accident.

### `terraform validate`
- Checks that configuration files are syntactically valid and internally consistent.
- Does **not** guarantee `apply` will succeed (e.g., won't catch permission or quota issues at the provider/API level).

## Key Takeaways
- The resource graph is the backbone of both `apply` and `destroy` — same dependency logic, opposite direction.
- `validate` catches syntax issues; it doesn't validate real-world provider behavior.
