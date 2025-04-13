1. What does the `resource` block define in Terraform?
   - A. A module for reuse
   - B. A variable for input
   - C. A specific infrastructure object
   - D. A provisioner script

2. What is the correct syntax for defining a resource block?
   - A. `resource "<TYPE>" "<PROVIDER>" {}`
   - B. `resource "<PROVIDER>_<TYPE>" "<NAME>" {}`
   - C. `resource "<NAME>" "<PROVIDER>" {}`
   - D. `resource "<PROVIDER>" "<NAME>" {}`
  
3. In the block below, what does `"web"` represent?
   ```hcl
   resource "aws_instance" "web" {
     ami           = "ami-1234"
     instance_type = "t2.micro"
   }
   ```
   - A. Provider
   - B. Resource type
   - C. Configuration key
   - D. Resource name

4. What does `count = 3` do in a resource block?
   - A. Updates the instance 3 times
   - B. Creates 3 copies of the resource
   - C. Deletes 2 and keeps 1
   - D. Multiplies the cost by 3

5. Which meta-argument allows resource creation based on a map or set?
   - A. `count`
   - B. `depends_on`
   - C. `for_each`
   - D. `lifecycle`

6. Which meta-argument helps ensure zero-downtime deployments?
   - A. `ignore_changes`
   - B. `create_before_destroy`
   - C. `prevent_destroy`
   - D. `depends_on`

7. What does the following code do?
   ```hcl
   depends_on = [aws_vpc.main]
   ```
   - A. Delays provisioning until manual confirmation
   - B. Sets a dependency that forces order of creation
   - C. Destroys resources before creation
   - D. Changes the VPC to depend on other resources

8. What is the purpose of the `lifecycle` block?
   - A. Create multiple resources
   - B. Schedule resource deletion
   - C. Fine-tune how Terraform handles changes
   - D. Define the lifespan of resources

9. Which lifecycle setting prevents accidental resource deletion?
   - A. `create_before_destroy`
   - B. `prevent_destroy`
   - C. `ignore_changes`
   - D. `destroy_only`

10. Which meta-argument would help you skip updates to specific attributes?
    - A. `prevent_destroy`
    - B. `ignore_changes`
    - C. `skip`
    - D. `count`

---

### ✅ **True or False**

11. The `for_each` argument works only with numeric values.  
12. `depends_on` is required for all resources in Terraform.  
13. Provisioners are ideal for every deployment process.  
14. You can access an element of a counted resource with square brackets.  
15. Tags help with auditing and cost management.  

---

### 📌 **Fill in the Blank**

16. `resource "aws_instance" "web" { ... }` — Here, `aws_instance` is the __________.  
17. The keyword used to define outputs is __________.  
18. To pass dynamic values to resources, we use __________.  
19. Terraform discourages the use of __________ due to their lack of idempotency.  
20. The default file where Terraform tracks real infrastructure is __________.  

---

### 🔄 **Matching**

21–25: Match the meta-argument to its description:

| Meta-Argument     | Description                                  |
|-------------------|----------------------------------------------|
| A. `count`        | 1. Skips changes to certain attributes       |
| B. `for_each`     | 2. Forces execution order                    |
| C. `depends_on`   | 3. Iterates over a map or set                |
| D. `lifecycle`    | 4. Adjusts resource handling during apply    |
| E. `ignore_changes`| 5. Creates multiple copies of a resource    |

---

### 🔍 **Scenario-Based**

26. You want to create one S3 bucket for each name in a list (`["media", "backup", "logs"]`). What should you use?

27. What happens if you remove a resource from your Terraform configuration and run `terraform apply`?

28. Why might you use `prevent_destroy` in a production environment?

29. You created 3 EC2 instances using `count = 3`. How would you reference the ID of the second instance?

30. You're importing an existing AWS instance with `terraform import`. What must you do next?

---

## ✅ **Answers – Terraform Resource Practice**

### 🔢 **Multiple Choice (Single Answer)**

1. **C** – A specific infrastructure object  
2. **B** – `resource "<PROVIDER>_<TYPE>" "<NAME>" {}`  
3. **D** – Resource name  
4. **B** – Creates 3 copies of the resource  
5. **C** – `for_each`  
6. **B** – `create_before_destroy`  
7. **B** – Sets a dependency that forces order of creation  
8. **C** – Fine-tune how Terraform handles changes  
9. **B** – `prevent_destroy`  
10. **B** – `ignore_changes`  

---

### ✅ **True or False**

11. **False** – `for_each` works with maps and sets, not just numbers  
12. **False** – `depends_on` is optional and only used when Terraform can’t infer dependencies  
13. **False** – Provisioners are discouraged and not ideal for all deployments  
14. **True** – E.g., `aws_instance.web[1].id`  
15. **True** – Tags help with cost tracking and identification  

---

### 📌 **Fill in the Blank**

16. **Resource type**  
17. **output**  
18. **variables**  
19. **provisioners**  
20. **terraform.tfstate**

---

### 🔄 **Matching**

| Question | Answer |
|----------|--------|
| 21       | **A → 5** – `count`: Creates multiple copies of a resource  
| 22       | **B → 3** – `for_each`: Iterates over a map or set  
| 23       | **C → 2** – `depends_on`: Forces execution order  
| 24       | **D → 4** – `lifecycle`: Adjusts resource handling during apply  
| 25       | **E → 1** – `ignore_changes`: Skips changes to certain attributes  

---

### 🔍 **Scenario-Based**

26. **Use `for_each` with a set or list**  
27. **Terraform will destroy the resource since it's no longer declared in config**  
28. **To avoid accidental deletion of critical infrastructure like databases or IAM roles**  
29. **`aws_instance.web[1].id`**  
30. **Write the matching resource block in configuration manually**
