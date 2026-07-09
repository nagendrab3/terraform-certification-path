# Day 8 — File Structure & Org

**Date:** Jul 7, 2026 | **Mod #6** | **Est. time:** 15 min

## Lessons Covered
- Terraform File Structure and Organization

## Notes

### Typical Project Layout
```
project/
├── main.tf          # primary resource definitions
├── variables.tf      # input variable declarations
├── outputs.tf         # output value declarations
├── providers.tf        # provider configuration
├── terraform.tfvars      # variable values (often gitignored if sensitive)
└── modules/
    └── <module-name>/
        ├── main.tf
        ├── variables.tf
        └── outputs.tf
```

### Organization Principles
- Split configuration by concern (resources, variables, outputs, providers) rather than one giant file.
- Use modules to encapsulate reusable, self-contained pieces of infrastructure.
- Keep environment-specific values (dev/staging/prod) separate — e.g., via `.tfvars` files or separate directories/workspaces.
- Add a `.gitignore` for `.terraform/`, `*.tfstate`, and `*.tfvars` files containing secrets.

## Key Takeaways
- Good file structure scales better as a project grows and makes collaboration easier.
- This wraps up the foundational modules — next up is deeper workflow topics like state management and variables.
