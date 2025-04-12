### Exam Tips: Terraform Resource Blocks

✅ **Know the structure**:
```hcl
resource "<PROVIDER>_<TYPE>" "<NAME>" {
  # arguments
}
```

✅ **Understand argument types**:
- **Required** vs. **Optional** arguments (check provider docs)
- Map, list, and nested blocks (like `tags`, `timeouts`, `boot_disk`)

✅ **State management**:
- Resources are tracked in the **Terraform state** (`.tfstate`), which Terraform uses to compare real vs desired infra.

✅ **Meta-arguments**:
- `depends_on`
- `provider`
- `count` and `for_each` for creating multiple instances dynamically
- `lifecycle`

✅ **Referencing resources**:
- Format: `resource_type.resource_name.attribute`
- Often used in outputs or other resources:
  ```hcl
  output "instance_ip" {
    value = aws_instance.web.public_ip
  }
  ```

✅ **Importing existing resources**:
- `terraform import` brings real-world infra into your state.

✅ **Avoid overusing provisioners**:
- Mentioned in the exam, but Terraform prefers using **remote state**, **user_data**, or proper IaC patterns instead.
