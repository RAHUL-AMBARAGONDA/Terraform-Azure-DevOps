# 🚀 Dev Module - Terraform Infrastructure

> **Environment**: Development  
> **Purpose**: Provisioning an Azure Kubernetes Service (**AKS**) cluster for the Dev environment using **Terraform**

---

## 📂 Directory Structure

```
Dev/
│── .terraform.lock.hcl    # 🔒 Provider lock file
│── backend.tf             # 📦 Remote backend configuration
│── main.tf                # 📜 Main infrastructure definition
│── terraform.tfvars       # ⚙️ Variable values for Dev
│── variables.tf           # 📌 Variable definitions
```

---

## 📄 File Descriptions

### 🔒 `.terraform.lock.hcl`
- Ensures consistent provider versions for Terraform deployments.
- Prevents unintended upgrades that might break infrastructure.
- Automatically generated when `terraform init` is run.

### 📦 `backend.tf`
- Defines **remote state storage** in Azure to enable collaboration.
- Ensures state consistency across multiple users working on the same infrastructure.
- Example:
  ```hcl
  terraform {
    backend "azurerm" {
      resource_group_name   = "tfstate-rg"
      storage_account_name  = "tfstatestorage"
      container_name        = "tfstate"
      key                   = "dev.terraform.tfstate"
    }
  }
  ```
- This avoids local state management issues and ensures **reliable infrastructure provisioning**.

### 📜 `main.tf`
- Defines all **Azure resources** for the Dev environment.
- Uses a **modular approach** to call the AKS module, ensuring reusability and maintainability.
- Example:
  ```hcl
  module "aks" {
    source              = "../Modules/AKS"
    resource_group_name = var.resource_group_name
    cluster_name        = var.cluster_name
    node_count          = var.node_count
  }
  ```
- This ensures that infrastructure code remains **scalable, reusable, and easy to manage**.

### ⚙️ `terraform.tfvars`
- Contains environment-specific values (**Dev environment**), allowing seamless configuration.
- Example:
  ```hcl
  resource_group_name = "dev-rg"
  cluster_name        = "dev-aks"
  node_count          = 2
  ```
- Helps separate Dev, Staging, and Production environments using different `terraform.tfvars` files.
- Ensures **configuration isolation** between environments.

### 📌 `variables.tf`
- Declares input variables for Terraform, ensuring flexibility and configurability.
- Example:
  ```hcl
  variable "resource_group_name" {
    type        = string
    description = "The name of the resource group"
  }

  variable "cluster_name" {
    type        = string
    description = "Name of the AKS cluster"
  }

  variable "node_count" {
    type        = number
    description = "Number of nodes in the AKS cluster"
    default     = 2
  }
  ```
- Allows **parameterized infrastructure provisioning** with minimal code changes.
- Improves code **reusability** and ensures easy modification of infrastructure parameters.

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
✔ Use **remote backend storage** (`backend.tf`) to avoid state conflicts and ensure team collaboration.  
✔ Store sensitive data in **Azure Key Vault** instead of hardcoding in `terraform.tfvars` for security best practices.  
✔ Use a **modular design** (`main.tf` calls reusable AKS module) to make infrastructure scalable.  
✔ Maintain separate `terraform.tfvars` files per environment (Dev, Staging, Prod) to isolate configurations.  
✔ Run `terraform fmt` before committing to ensure standardized formatting.  
✔ Implement `terraform validate` to check for syntax errors before applying changes.  
✔ Use **role-based access control (RBAC)** for security when deploying infrastructure in Azure.  
✔ Follow **Infrastructure as Code (IaC) principles** to make the infrastructure repeatable and maintainable.  
✔ Implement **Terraform workspaces** for managing multiple environments within the same repository.  
✔ Use **Terraform modules** for abstraction and reusability to simplify complex infrastructure.

---

🔗 **References**
- [Terraform Azure Provider Docs](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs)
- [Azure Kubernetes Service (AKS)](https://learn.microsoft.com/en-us/azure/aks/)
- [Best Practices for Terraform](https://learn.hashicorp.com/terraform)
- [Terraform Backend Configuration](https://developer.hashicorp.com/terraform/language/settings/backends/configuration)

---

💡 *Maintained by [Rahul Ambaragonda]*
