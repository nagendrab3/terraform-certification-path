# Day 11 — Config Fundamentals III

**Date:** Jul 10, 2026 | **Mod #7** | **Est. time:** 55 min

## Lessons Covered
- Input Variables
- Variable Types
- Variable Precedence
- Output Values
- Lab: Variables & Outputs

## Notes

### Input Variables
- Declared in a `variable` block, used to parameterize configuration instead of hardcoding values.
```hcl
  variable "instance_type" {
    type    = string
    default = "t2.micro"
  }
```
- Referenced elsewhere as `var.instance_type`.

### Variable Types
- Common types: `string`, `number`, `bool`, `list(...)`, `map(...)`, `object({...})`, `set(...)`.
- Type constraints help catch mistakes early (e.g., passing a string where a number is expected).

### Variable Precedence
From **lowest to highest priority** (later sources override earlier ones):
1. Environment variables (`TF_VAR_name`)
2. `terraform.tfvars` file
3. `*.auto.tfvars` files (alphabetical order)
4. `-var-file` flag on the CLI
5. `-var` flag on the CLI (highest precedence)

### Output Values
- Declared in an `output` block to surface useful values after `apply` (e.g., an instance's public IP).
```hcl
  output "instance_ip" {
    value = aws_instance.web.public_ip
  }
```
- Useful for chaining modules together or for quick visibility into `apply` results.

### Lab: Variables & Outputs
- Hands-on: parameterized a configuration with input variables and exposed key values via outputs.

## Key Takeaways
- Variables make configuration reusable across environments; understanding precedence is critical for debugging "why did it use that value?" issues.
- Outputs are how modules and CLI users get visibility into resource attributes without digging into state manually.
