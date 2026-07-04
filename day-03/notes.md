# Day 3 — Terraform Foundations I

**Date:** Jul 2, 2026 | **Mod #3** | **Est. time:** 45 min

## Lessons Covered
- Intro to Terraform
- HCL Basics
- Resource Referencing demo

## Notes

### Intro to Terraform
- Terraform is an open-source IaC tool created by HashiCorp.
- Uses a **declarative** model: you describe the desired end state, and Terraform figures out how to get there.

### HCL Basics
- HCL = HashiCorp Configuration Language.
- Blocks are defined using curly braces `{ }`.
- Core block types: `provider`, `resource`, `variable`, `output`, `data`.
- Config files use the `.tf` extension.

### Resource Referencing
- One resource's attribute can be referenced as input to another, e.g.:
  ```hcl
  resource "aws_instance" "web" {
    subnet_id = aws_subnet.main.id
  }
  ```
- This creates an **implicit dependency** — Terraform automatically infers the order of creation from the reference.

## Key Takeaways
- Declarative + HCL + resource referencing = Terraform can build a dependency graph automatically, without manual sequencing.
