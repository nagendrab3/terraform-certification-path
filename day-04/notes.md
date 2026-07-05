# Day 4 — Terraform Foundations II

**Date:** Jul 3, 2026 | **Mod #3** | **Est. time:** 30 min

## Lessons Covered
- HCL Best Practices
- Core Components & Benefits
- Version Selection
- Comparing Tools
- Declarative vs Imperative
- Quiz

## Notes

### HCL Best Practices
- Use consistent naming conventions.
- Organize code into logical files: `main.tf`, `variables.tf`, `outputs.tf`.
- Use variables instead of hardcoding values.
- Comment where intent isn't obvious.

### Core Components & Benefits
- Providers + core engine + state = how Terraform manages infrastructure.
- Benefits: provider-agnostic, human-readable config, version-controllable, predictable plan/apply workflow.

### Version Selection
- Pin Terraform CLI and provider versions to avoid unexpected breaking changes.
- Consider module/provider compatibility requirements when choosing a version.

### Comparing Tools
- Terraform vs other IaC tools: declarative model, strong provider ecosystem, built-in state tracking.
- Understanding trade-offs helps clarify *why* Terraform makes certain design choices.

### Declarative vs Imperative
- **Declarative:** describe desired end state (Terraform).
- **Imperative:** describe exact steps to reach a state (shell scripts).
- Declarative tools handle ordering/dependencies for you via a resource graph.

## Key Takeaways
- This module is conceptual — it explains *why* the workflow (plan → apply) is designed the way it is.
