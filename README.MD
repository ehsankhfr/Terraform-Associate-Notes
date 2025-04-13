![Terraform](https://img.shields.io/badge/IaC-Terraform-blue)
# 📘 Terraform Associate (003) Study Guide

Welcome to the **Terraform Associate (003)** certification prep repo! This repository is a comprehensive and structured guide to help you study and practice for the **HashiCorp Certified: Terraform Associate (003)** exam.

## 🔍 About

This repo is designed to serve as a modular and in-depth study companion. It breaks down the core concepts covered in the certification into digestible, exam-aligned sections with:

- Concise explanations
- Examples and real-world usage
- Exam-style questions (MCQs)
- Detailed answer keys with reasons

All notes and questions are curated to reflect the official Terraform Associate 003 exam objectives.

---

## 📂 Folder Structure

Each topic is covered in two parts:

1. **Topic Markdown (`XX.01-Topic.MD`)**: Deep dives into the core Terraform concept, syntax, commands, and use cases.
2. **Exam Markdown (`XX.02-Topic-Exam.MD`)**: Practice set of 20–30 exam-style questions with answers and explanations.

Here's a quick overview of what's covered:

| File | Description |
|------|-------------|
| [01.01-Introduction.MD](01.01-Introduction.MD) | Overview of Terraform and the exam |
| [01.02-Introduction-Exam.MD](01.02-Introduction-Exam.MD) | Questions on intro and exam scope |
| [02.01-Resources.MD](02.01-Resources.MD) | Terraform resources and their configuration |
| [02.02-Resource-Lifecycle.MD](02.02-Resource-Lifecycle.MD) | Resource lifecycle (`create_before_destroy`, `prevent_destroy`) |
| [02.03-Resources-Providers&Data.MD](02.03-Resources-Providers&Data.MD) | Working with providers and data sources |
| [02.04-Resources-Exam.MD](02.04-Resources-Exam.MD) | Resource-related questions |
| [03.01-State.MD](03.01-State.MD) | Terraform state, remote state |
| [03.02-State-Workspace.MD](03.02-State-Workspace.MD) | Workspaces and their usage |
| [03.03-State-Exam.MD](03.03-State-Exam.MD) | Questions on state and workspaces |
| [04.01-Variables.MD](04.01-Variables.MD) | Input variables, locals, outputs |
| [04.02-Variables-Exam.MD](04.02-Variables-Exam.MD) | Questions on variables |
| [05.01-Provisioners.MD](05.01-Provisioners.MD) | Usage of provisioners in Terraform |
| [05.02-Provisioners-Exam.MD](05.02-Provisioners-Exam.MD) | Questions on provisioners |
| [06.01-Modules.MD](06.01-Modules.MD) | Terraform modules and best practices |
| [06.02-Modules-Exam.MD](06.02-Modules-Exam.MD) | Questions on modules |
| [07.01-Builtin-Functions-and-Type-Constraints.MD](07.01-Builtin-Functions-and-Type-Constraints.MD) | Built-in functions and type systems |
| [07.02-Builtin-Functions-and-Type-Constraints-Exam.MD](07.02-Builtin-Functions-and-Type-Constraints-Exam.MD) | Questions on functions and types |
| [08.01-Dynamic-Blocks.MD](08.01-Dynamic-Blocks.MD) | Dynamic blocks and their use |
| [08.02-Dynamic-Blocks-Exam.MD](08.02-Dynamic-Blocks-Exam.MD) | Questions on dynamic blocks |
| [09.01-Commands-And-Terraform-Config.MD](09.01-Commands-And-Terraform-Config.MD) | Terraform CLI commands, configuration |
| [09.02-Commands-And-Terraform-Config.MD](09.02-Commands-And-Terraform-Config.MD) | Questions on commands/config |
| [10.01-Debug-and-Terraform-CloudEnterprise.MD](10.01-Debug-and-Terraform-CloudEnterprise.MD) | Debugging, Terraform Cloud/Enterprise, Sentinel, Vault |
| [10.02-Debug-and-Terraform-CloudEnterprise-Exam.MD](10.02-Debug-and-Terraform-CloudEnterprise-Exam.MD) | Questions on advanced and enterprise topics |

---

## 🎯 Who This Repo Is For

- Anyone preparing for the **Terraform Associate 003 exam**
- Engineers new to Terraform
- Developers looking to strengthen IaC (Infrastructure as Code) fundamentals
- DevOps/SRE professionals seeking HashiCorp certification

---

## ✅ How to Use

1. Start from the lowest-numbered topic and work your way up.
2. Read the concept file first (`XX.01-*.MD`)
3. Test yourself with the question file (`XX.02-*-Exam.MD`)
4. Check answers and read the reasoning
5. Repeat for all sections

---

## 🛠️ Tools Recommended

- [Terraform CLI](https://developer.hashicorp.com/terraform/downloads)
- [Terraform Cloud](https://app.terraform.io/)
- A code editor like **VSCode**
- Terminal and Git

---

## 🧠 Bonus Tips

- Spin up and destroy test resources using `terraform apply` / `destroy` for hands-on practice.
- Use `terraform console` to test expressions, functions, and outputs.
- Practice building and destroying modules and remote state setups.

---

## 📜 License

This content is open-source and free to use under the [MIT License](LICENSE.MD).
