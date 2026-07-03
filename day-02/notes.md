# Day 2 — Preparing Your Environment

**Date:** Jul 1, 2026 | **Mod #2** | **Est. time:** 35 min

## Lessons Covered
- Install Terraform (Mac/Linux/Win)
- Install VS Code
- AWS/Azure/GitHub credential setup

## Notes

### Installing Terraform
- Download the appropriate binary/package for your OS, or use a package manager.
- Verify install with `terraform version`.

### Installing VS Code
- Recommended editor for writing HCL.
- Install the HashiCorp Terraform extension for syntax highlighting and validation support.

### Credential Setup
- **AWS/Azure:** Configure access keys/secrets (or equivalent auth method) so Terraform can authenticate against the provider's API.
- **GitHub:** Set up credentials to support version-controlling `.tf` configuration files and collaborating with a team.

## Key Takeaways
- Working authentication must be in place *before* running `apply` against real infrastructure.
- Version control from day one keeps configuration changes auditable.
