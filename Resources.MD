## 🔹 1. What is a Terraform Resource?

A **resource** is the **primary unit of infrastructure** in Terraform. It defines a component such as a virtual machine, a DNS record, a security group, etc.

Each resource block manages **one specific object** in your cloud provider (AWS, Azure, GCP, etc.).

---

## 🔹 2. Syntax Breakdown

```hcl
resource "<PROVIDER>_<TYPE>" "<NAME>" {
  # configuration arguments
}
```

### Example:
```hcl
resource "aws_instance" "web" {
  ami           = "ami-0c55b159cbfafe1f0"
  instance_type = "t2.micro"
  tags = {
    Name = "WebServer"
  }
}
```

- `aws_instance` → provider + resource type
- `web` → local resource name
- Attributes inside define resource behavior

---

## 🔹 3. Common Configuration Arguments

- **Required**: Each provider/resource has mandatory fields (e.g., `ami`, `instance_type` for AWS EC2)
- **Optional**: You can define behavior using tags, metadata, networking, etc.

### Data Types You Might See:
- `string`, `number`, `bool`
- `list`, `map`, `set`
- **Nested blocks**: like `timeouts`, `boot_disk`, `connection`

---

## 🔹 4. Meta-Arguments

These are built-in arguments that apply to **all** resources:

### 🟠 `count`
Creates **multiple instances** of a resource:

```hcl
resource "aws_instance" "web" {
  count         = 3
  ami           = "ami-1234"
  instance_type = "t2.micro"
}
```

Access each with:  
`aws_instance.web[0].id`, `aws_instance.web[1].id`, etc.

---

### 🟠 `for_each`
Used for more control with maps and sets:

```hcl
resource "aws_s3_bucket" "buckets" {
  for_each = toset(["logs", "images", "archive"])
  bucket   = each.key
  acl      = "private"
}
```

Access: `aws_s3_bucket.buckets["logs"].id`

---

### 🟠 `depends_on`
Force explicit dependencies between resources:

```hcl
depends_on = [aws_vpc.main]
```

Usually not needed unless Terraform can’t infer the dependency.

---

### 🟠 `lifecycle`
Control Terraform’s behavior when applying changes:

```hcl
lifecycle {
  create_before_destroy = true
  prevent_destroy = true
  ignore_changes = [tags]
}
```

- `create_before_destroy`: helpful for zero-downtime deployments  
- `prevent_destroy`: stops accidental deletion  
- `ignore_changes`: skips updating certain attributes

---

## 🔹 5. Referencing Other Resources

Terraform lets you **reference other resources' attributes**:

```hcl
resource "aws_eip" "ip" {
  instance = aws_instance.web.id
}
```

You can reference outputs and use them elsewhere.

---

## 🔹 6. Tagging and Metadata

Tagging is important for billing, auditing, and identification:

```hcl
tags = {
  Name        = "web-server"
  Environment = var.environment
}
```

Some cloud providers support labels instead of tags (like GCP).

---

## 🔹 7. Provisioners (Use With Caution)

Used to run scripts **on the created resources**, e.g. to install software.

```hcl
provisioner "remote-exec" {
  inline = [
    "sudo apt-get update",
    "sudo apt-get install nginx -y"
  ]
}
```

### ⚠️ Provisioners are discouraged:
- Not idempotent
- Prone to failure
- Use only when necessary (e.g., breaking glass situations)

---

## 🔹 8. Importing Existing Resources

Sometimes you want Terraform to manage existing infra.

```bash
terraform import aws_instance.web i-1234567890abcdef0
```

- This **adds the resource to state** but you must also write its config manually.
- Useful for migration to Terraform.

---

## 🔹 9. Outputs and Variables in Resources

### 📤 Outputs:
```hcl
output "instance_ip" {
  value = aws_instance.web.public_ip
}
```

### 📥 Variables:
```hcl
variable "instance_type" {
  default = "t2.micro"
}

resource "aws_instance" "web" {
  instance_type = var.instance_type
}
```

Use variables to make configs reusable and dynamic.

---

## 🔹 10. Best Practices

✅ Use consistent naming (like `resource_type_environment_role`)  
✅ Tag all resources  
✅ Keep modules reusable  
✅ Avoid hardcoding values  
✅ Minimize use of provisioners  
✅ Use `terraform fmt` to keep your code clean  
✅ Version control everything

---

## 🔹 11. Common Resource Types by Provider (for Exam)

### AWS:
- `aws_instance`
- `aws_vpc`
- `aws_s3_bucket`
- `aws_security_group`
- `aws_iam_role`

### Azure:
- `azurerm_resource_group`
- `azurerm_virtual_network`
- `azurerm_network_interface`
- `azurerm_linux_virtual_machine`

### GCP:
- `google_compute_instance`
- `google_storage_bucket`
- `google_project`
- `google_service_account`

---

## 🧠 Exam-Specific Tips

📝 Expect questions about:
- How `count` vs. `for_each` behaves
- What `depends_on` does
- Why provisioners are discouraged
- What happens when a resource is removed from config
- Lifecycle behaviors (`prevent_destroy`, `ignore_changes`)
- How to reference other resources
