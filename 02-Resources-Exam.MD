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
