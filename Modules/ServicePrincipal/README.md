# 🚀 Terraform Module - Infrastructure Setup

> **Environment**: Development / Staging / Production  
> **Purpose**: This module is designed to provision essential cloud resources using **Terraform** for a scalable and maintainable infrastructure.

---

## 📂 Directory Structure

```
Module/
│── main.tf       # 📜 Defines the core infrastructure components
│── output.tf     # 📤 Specifies output values for Terraform
│── variables.tf  # 📌 Defines input variables for flexibility
```

---

## 📄 File Descriptions

### 📜 `main.tf`
- This file contains the main Terraform configuration, defining the required cloud resources.
- It provisions essential infrastructure such as virtual machines, storage accounts, or networking components.
- Example usage:
  ```hcl
  resource "azurerm_resource_group" "example" {
    name     = var.resource_group_name
    location = var.location
  }
  ```
- This ensures infrastructure is **declarative, repeatable, and scalable**.

### 📤 `output.tf`
- Defines outputs to extract useful information from the Terraform state.
- Outputs provide values such as resource IDs, public IP addresses, or connection strings.
- Example:
  ```hcl
  output "resource_group_name" {
    value = azurerm_resource_group.example.name
  }
  ```
- Helps users retrieve important details for further automation or configuration.

### 📌 `variables.tf`
- Declares input variables for dynamic and configurable deployments.
- Example:
  ```hcl
  variable "resource_group_name" {
    type        = string
    description = "The name of the resource group"
  }
  
  variable "location" {
    type        = string
    description = "The Azure region for resource deployment"
    default     = "East US"
  }
  ```
- Improves code **flexibility and maintainability**.

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
3️⃣ **Apply changes and provision the infrastructure**
```sh
terraform apply
```
4️⃣ **Destroy the infrastructure when no longer needed**
```sh
terraform destroy
```

---

## ✅ Best Practices
✔ Keep variables configurable in `variables.tf` to improve reusability.  
✔ Use **remote state storage** for collaboration and consistency.  
✔ Implement `terraform fmt` to ensure code is formatted properly.  
✔ Validate configurations before applying using `terraform validate`.  
✔ Keep sensitive values in **Terraform Cloud Vault or Azure Key Vault**.  

---

🔗 **References**
- [Terraform Azure Provider Docs](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs)
- [Terraform Best Practices](https://learn.hashicorp.com/terraform)
- [Terraform Output Values](https://developer.hashicorp.com/terraform/language/values/outputs)

---

💡 *Maintained by [RAHUL AMBARAGONDA]*
