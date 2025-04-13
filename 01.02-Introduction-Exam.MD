### **1. What is the main goal of Infrastructure as Code (IaC)?**  
A. To allow developers to build UI code faster  
B. To write scripts to update DNS manually  
C. To automate infrastructure provisioning via code  
D. To manage databases with Python

---

### **2. IaC helps eliminate which kind of environment?**  
A. Cloud-native  
B. Snowflake  
C. Immutable  
D. Stateless

---

### **3. Which of the following is NOT a benefit of IaC?**  
A. Repeatable deployments  
B. Manual intervention required  
C. Cost optimization  
D. Reduced misconfiguration risk

---

### **4. True or False:** Terraform follows an **imperative** approach.

---

### **5. What is an example of a declarative statement in Terraform?**  
A. “Use for loop to create 3 servers”  
B. “Run bash script to make EC2”  
C. “Create EC2 instances in us-west-2”  
D. “SSH into server and install Nginx”

---

### **6. Which IaC tool is declarative by nature?**  
A. Ansible (scripts only)  
B. Shell scripts  
C. Terraform  
D. Bash with AWS CLI

---

### **7. What are the three phases of the standard Terraform workflow?**  
A. Init → Deploy → Update  
B. Plan → Approve → Provision  
C. Write → Plan → Apply  
D. Plan → Apply → Destroy

---

### **8. What does `terraform init` NOT do?**  
A. Download provider plugins  
B. Format your Terraform code  
C. Set up the backend  
D. Initialize working directory

---

### **9. When should you run `terraform init` again?**  
A. After adding a new provider  
B. After running `terraform destroy`  
C. After every `terraform apply`  
D. After changing outputs

---

### **10. What does `terraform plan` do?**  
A. Runs the code and deploys resources  
B. Checks syntax and provider validity  
C. Shows what Terraform will do without making changes  
D. Connects to the state backend

---

### **11. True or False:** `terraform plan` modifies the infrastructure.

---

### **12. What does `terraform apply` do after applying the plan?**  
A. Deletes the state file  
B. Updates the backend  
C. Updates the state file  
D. Refactors modules

---

### **13. What is the default file used to store Terraform state?**  
A. `main.tf`  
B. `terraform.state`  
C. `infra.json`  
D. `terraform.tfstate`

---

### **14. Which command destroys all provisioned infrastructure?**  
A. `terraform teardown`  
B. `terraform remove`  
C. `terraform destroy`  
D. `terraform kill`

---

### **15. True or False:** `terraform destroy` must access the state file to work.

---

### **16. Which of these Terraform commands formats code?**  
A. `terraform format`  
B. `terraform lint`  
C. `terraform validate`  
D. `terraform fmt`

---

### **17. Which of these validates configuration file syntax?**  
A. `terraform fmt`  
B. `terraform check`  
C. `terraform validate`  
D. `terraform output`

---

### **18. True or False:** `terraform validate` checks the cloud provider credentials.

---

### **19. Which command shows values from your output blocks?**  
A. `terraform show`  
B. `terraform output`  
C. `terraform inspect`  
D. `terraform var`

---

### **20. Which command displays the full state in human-readable form?**  
A. `terraform read`  
B. `terraform log`  
C. `terraform show`  
D. `terraform config`

---

### **21. What is one reason to store Terraform code in a GitHub repo?**  
A. To avoid using `terraform apply`  
B. To store backups of `terraform.tfstate`  
C. For CI/CD collaboration and version control  
D. To host the website

---

### **22. Which of these is the correct file extension for Terraform code?**  
A. `.tfscript`  
B. `.terraform`  
C. `.tf`  
D. `.yml`

---

### **23. What should be done before running `terraform apply`?**  
A. Create an S3 bucket  
B. Review the execution plan  
C. Run `terraform destroy`  
D. Upload config to cloud

---

### **24. Which command is the safest to run first when cloning someone else’s Terraform project?**  
A. `terraform plan`  
B. `terraform init`  
C. `terraform show`  
D. `terraform destroy`

---

### **25. What does the state file track?**  
A. Logs of CLI commands  
B. Differences between resource definitions  
C. Relationships between variables  
D. Real infrastructure managed by Terraform

---

### **26. What happens if the state file is missing?**  
A. Terraform will error out  
B. Terraform will download a new one  
C. Terraform will skip planning  
D. Terraform will auto-create one in GitHub

---

### **27. What does `terraform output` help with?**  
A. Showing resources created  
B. Displaying formatted JSON  
C. Surfacing variables marked as `output`  
D. Restarting state

---

### **28. Which CLI tool is used to install Terraform manually?**  
A. `brew`  
B. `apt`  
C. `yum`  
D. All of the above

---

### **29. What is a best practice after unzipping Terraform manually?**  
A. Run it as root  
B. Add it to system’s `$PATH`  
C. Use Docker  
D. Create a `.tf` file

---

### **30. True or False:** After installing Terraform, it can be used without restarting the shell or terminal.

---

| #  | Answer |
|----|--------|
| 1  | C      |
| 2  | B      |
| 3  | B      |
| 4  | False  |
| 5  | C      |
| 6  | C      |
| 7  | C      |
| 8  | B      |
| 9  | A      |
| 10 | C      |
| 11 | False  |
| 12 | C      |
| 13 | D      |
| 14 | C      |
| 15 | True   |
| 16 | D      |
| 17 | C      |
| 18 | False  |
| 19 | B      |
| 20 | C      |
| 21 | C      |
| 22 | C      |
| 23 | B      |
| 24 | B      |
| 25 | D      |
| 26 | A      |
| 27 | C      |
| 28 | D      |
| 29 | B      |
| 30 | False  |
