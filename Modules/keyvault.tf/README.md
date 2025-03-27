# 🚀 Terraform Module - Infrastructure Deployment

> **Purpose**: This module automates the deployment of infrastructure resources using **Terraform**.

---

## 📂 Directory Structure

```
Module/
│── main.tf        # 📜 Main Terraform configuration
│── output.tf      # 📤 Output values definition
│── variables.tf   # 📌 Input variables definition
```

---

## 📄 File Descriptions

### 📜 `main.tf`
- Defines the core **infrastructure resources**.
- Uses input variables for flexibility and scalability.
- Example:
  ```hcl
  resource "azurerm_resource_group" "example" {
    name     = var.resource_group_name
    location = var.location
  }
  ```
- Ensures **declarative infrastructure** management.

### 📤 `output.tf`
- Defines the **output values** that provide useful information after deployment.
- Example:
  ```hcl
  output "resource_group_name" {
    value = azurerm_resource_group.example.name
  }
  ```
- Helps in retrieving important data dynamically.

### 📌 `variables.tf`
- Declares **input variables**, making the module configurable.
- Example:
  ```hcl
  variable "resource_group_name" {
    type        = string
    description = "Name of the resource group"
  }

  variable "location" {
    type        = string
    description = "Azure region for resource deployment"
  }
  ```
- Ensures **flexibility** across different environments.

---

## 🚀 How to Use This Module

1️⃣ **Initialize Terraform**
```sh
terraform init
```
2️⃣ **Plan the infrastructure changes**
```sh
terraform plan
```
3️⃣ **Apply changes and provision resources**
```sh
terraform apply
```
4️⃣ **Destroy resources if needed**
```sh
terraform destroy
```

---

## ✅ Best Practices
✔ Use **remote backend storage** for state management.
✔ Store sensitive values in **environment variables or Terraform Vault**.
✔ Maintain a **modular approach** for scalable infrastructure.
✔ Use `terraform fmt` to format code for consistency.
✔ Validate configurations using `terraform validate` before applying.
✔ Implement **role-based access control (RBAC)** for security.

---

🔗 **References**
- [Terraform Documentation](https://developer.hashicorp.com/terraform)
- [Azure Terraform Provider](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs)
- [Infrastructure as Code Best Practices](https://learn.hashicorp.com/terraform)

---

💡 *Maintained by [RAHUL AMBARAGONDA]*
