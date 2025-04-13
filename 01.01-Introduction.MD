## 🧱 1. What is Infrastructure as Code (IaC)?

### 🔹 Definition
**Infrastructure as Code** is the practice of managing and provisioning infrastructure (servers, networks, databases, etc.) through **machine-readable configuration files** rather than manual processes or GUIs.

---

### 🔹 Key Benefits

✅ **Repeatability & Consistency**
- Avoids "snowflake" environments by codifying every infrastructure component.
- Every deployment is predictable and repeatable.

✅ **Version Control & Auditability**
- Code can be stored in Git (or other VCS), reviewed, tracked, and reverted.
- Teams can collaborate on infrastructure the same way they do with application code.

✅ **Automated Deployment**
- IaC allows automation pipelines to provision, update, or tear down infrastructure **without human interaction**.

✅ **Speed & Efficiency**
- Reduces the manual overhead of navigating web portals or CLIs.

✅ **Reduced Risk**
- Minimizes misconfigurations and human error.

✅ **Cost Optimization**
- Automatically destroy unused resources to avoid unnecessary cloud bills.

---

### 🔹 Declarative vs Imperative

| Declarative                        | Imperative                          |
|-----------------------------------|-------------------------------------|
| You **describe the desired state**| You **specify step-by-step** how to achieve it |
| Terraform is **declarative**      | Shell scripts, Ansible (sometimes) are imperative |
| Example: “I want 3 EC2 instances” | Example: “Run this script to create EC2 instance” |

---

## 🧩 2. Terraform Workflow (Standard Lifecycle)

Terraform follows a consistent 3-phase workflow:

---

### 🟪 1. **Write**

- Write Terraform configuration files using `.tf` or `.tf.json`.
- Files describe the infrastructure and use:
  - **Resources** (infrastructure components)
  - **Data sources**
  - **Variables & outputs**
  - **Modules**

✅ Best Practice: Store the code in a **GitHub repo** for collaboration and CI/CD.

---

### 🟪 2. **Plan**

Use the `terraform plan` command to:
- See what Terraform intends to do.
- Review resource additions, changes, and deletions.
- Safely validate changes **before** they happen.

---

### 🟪 3. **Apply**

Apply your infrastructure changes using `terraform apply`:
- Executes the plan and provisions infrastructure.
- Changes are **recorded in the state file**.
- Terraform compares your config with the current state to decide what actions to take.

---

### Bonus: **Review/Refactor Loop**
- Refactor code over time.
- Store modules, split files, add inputs/outputs for better reuse.

---

## 🔧 3. Core Terraform Commands – Certification Focus

---

### ⚙️ `terraform init`

- Initializes the Terraform working directory.
- Downloads required providers (like AWS, Azure).
- Installs any modules defined in your config.
- Sets up the backend (e.g., local or remote state).

📌 **Must be run first**, anytime you:
- Clone a repo
- Add/change providers
- Change backends

---

### 🧐 `terraform plan`

- Creates an **execution plan**.
- Shows what actions will be taken.
- Does **not** make any changes.

✅ Useful for code review or approval processes.

---

### 🚀 `terraform apply`

- Applies the infrastructure changes.
- Prompts for confirmation unless `-auto-approve` is used.
- Updates the **state file** after execution.

📁 Terraform State File:
- Tracks real infrastructure resources
- By default, stored as `terraform.tfstate` (can be remote in S3, etc.)

---

### 💣 `terraform destroy`

- Destroys **all** resources defined in your config.
- Uses the state file to identify what to destroy.
- **Irreversible!** Always double-check and back up your state.

---

### 🧼 `terraform fmt` (formatting)

- Formats `.tf` files to Terraform's standard style.
- Keeps code clean and consistent.

---

### ✅ `terraform validate`

- Validates configuration files for syntax and internal logic.
- Does **not** access providers or state.

---

### 🧠 `terraform show`, `terraform output`

- `show`: Displays the current state
- `output`: Displays values from the `output` blocks

---

## 📦 4. Installing Terraform – For Hands-On Exam Practice

---

### 🔹 Method 1: Manual Installation

1. Go to: [terraform.io/downloads](https://terraform.io/downloads)
2. Download appropriate binary (based on OS)
3. Unzip the binary
4. Move it to a directory in your system’s `$PATH` (e.g., `/usr/local/bin`)

---

### 🔹 Method 2: Use a Package Manager (Linux)

#### Debian/Ubuntu:
```bash
sudo apt-get update && sudo apt-get install -y gnupg software-properties-common
wget -O- https://apt.releases.hashicorp.com/gpg | gpg --dearmor | sudo tee /usr/share/keyrings/hashicorp-archive-keyring.gpg
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list
sudo apt update
sudo apt install terraform
```

#### RHEL/Amazon Linux:
```bash
sudo yum install -y yum-utils
sudo yum-config-manager --add-repo https://rpm.releases.hashicorp.com/AmazonLinux/hashicorp.repo
sudo yum -y install terraform
```

---

## 📘 Extra Tips for the Exam

📝 **Expect questions around:**
- Declarative vs imperative IaC
- Benefits of IaC (e.g., versioning, automation)
- Terraform workflow (init → plan → apply)
- State file and its importance
- Common commands and their purpose
- Safe usage of `destroy`
- Install paths and CLI basics

🧪 Practice Scenarios:
- “What happens if you run `terraform apply` without `terraform init`?”
- “You want to see what Terraform will do but not make changes. What command?”
- “You need to change 3 AWS resources. How can you see a summary first?”
- “Where is the state stored by default?”
