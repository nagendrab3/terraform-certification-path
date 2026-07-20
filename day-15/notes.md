# Day 15 — Reusable Code I

**Date:** Jul 15, 2026 | **Mod #9** | **Est. time:** 45 min

## Lessons Covered
- Built-in Functions + Lab
- Dynamic Values + Lab

## Notes

### Built-in Functions
- Terraform ships with many built-in functions for string manipulation, collections, math, encoding, date/time, etc. There are **no user-defined functions** in HCL — you can only use what Terraform provides.
- Common examples:
  - String: `upper()`, `lower()`, `join()`, `split()`, `trim()`, `format()`
  - Collection: `length()`, `merge()`, `concat()`, `contains()`, `lookup()`
  - Type conversion: `tostring()`, `tonumber()`, `tolist()`, `toset()`
  - Encoding: `jsonencode()`, `jsondecode()`, `base64encode()`
- Test functions safely using the Terraform console: `terraform console`, then try expressions interactively (e.g., `upper("hello")`) without touching real infrastructure.

### Lab: Built-in Functions
- Hands-on: used functions like `join()` and `format()` to dynamically construct resource names/tags rather than hardcoding strings.

### Dynamic Values
- Values that aren't hardcoded but computed from other data — variables, resource attributes, data source outputs, or function results.
- Enables configuration that adapts based on inputs rather than needing separate hardcoded blocks per case.
- Ties directly into `locals`, `count`, and `for_each` (covered in the next couple of days) as the mechanisms for actually generating dynamic/repeated resources.

### Lab: Dynamic Values
- Hands-on: built an expression that computes a value at plan time (e.g., a tag combining environment + a function-transformed string) instead of typing it manually.

## Key Takeaways
- Built-in functions are how you avoid hardcoding and keep configuration DRY (Don't Repeat Yourself).
- `terraform console` is a safe sandbox to experiment with functions and expressions before using them in real config.
