# Day 12 — Config Fundamentals IV

**Date:** Jul 11, 2026 | **Mod #7** | **Est. time:** 45 min

## Lessons Covered
- Lab: Multiple Resources & Dependencies
- Lab: Multi-Region Deploy
- Controlling TF Behavior/Settings
- Quiz

## Notes

### Lab: Multiple Resources & Dependencies
- Practiced chaining several resources together via implicit dependencies (resource referencing) and observing how Terraform sequences creation using the resource graph.

### Lab: Multi-Region Deploy
- Applied provider aliasing (from Day 9) in a real scenario — deploying resources to two AWS regions in a single configuration using aliased provider blocks and the `provider` meta-argument.

### Controlling Terraform Behavior/Settings
- The `terraform` block configures settings for the configuration itself (not a specific provider):
```hcl
  terraform {
    required_version = ">= 1.5.0"
    required_providers {
      aws = {
        source  = "hashicorp/aws"
        version = "~> 5.0"
      }
    }
  }
```
- `required_version` pins the Terraform CLI version allowed to run this config.
- `required_providers` pins provider source and version constraints — protects against unexpected breaking changes.
- Lifecycle meta-arguments (`create_before_destroy`, `prevent_destroy`, `ignore_changes`) can also be set per-resource to control behavior during apply/destroy.

## Key Takeaways
- This wraps up Config Fundamentals — variables, outputs, providers, resources, data sources, and now settings/lifecycle controls are all in place.
- Version pinning (`required_version`, `required_providers`) is a best practice that prevents "it worked yesterday" surprises.
