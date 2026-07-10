# Day 9 — Config Fundamentals I

**Date:** Jul 8, 2026 | **Mod #7** | **Est. time:** 40 min

## Lessons Covered
- Block Structure
- Provider Blocks
- Lab: Getting Started w/ AWS
- Multiple Providers

## Notes

### Block Structure
- A Terraform block generally has three parts: **block type**, **labels**, and the **arguments/body** in `{ }`.
- Example:
```hcl
  resource "aws_instance" "web" {
    ami           = "ami-123456"
    instance_type = "t2.micro"
  }
```
- `resource` = block type, `"aws_instance"` = resource type, `"web"` = local name used to reference this resource elsewhere.

### Provider Blocks
- Configure the settings (region, credentials, etc.) Terraform needs to talk to a specific platform's API.
- Typically the first block written in a new project, before any resources.
- Example:
```hcl
  provider "aws" {
    region = "us-east-1"
  }
```

### Lab: Getting Started w/ AWS
- Practiced writing a minimal provider + resource configuration and running the core workflow (`init` → `plan` → `apply`) against real AWS.

### Multiple Providers
- Use the `alias` argument to configure more than one instance of the same provider (e.g., two AWS regions).
```hcl
  provider "aws" {
    region = "us-west-2"
    alias  = "west"
  }
```
- Target a specific aliased provider on a resource with the `provider` meta-argument:
```hcl
  resource "aws_instance" "backup" {
    provider = aws.west
  }
```
- A resource with no `provider` meta-argument set uses the **default (unaliased)** provider configuration.
- Also used to manage entirely different platforms in one config (e.g., AWS + Azure), each needing its own provider block.

## Key Takeaways
- Provider blocks must exist and be valid before resources tied to that provider can be created.
- Aliasing is the mechanism for multi-region or multi-account setups within a single provider type.
