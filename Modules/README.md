# 🚀 Terraform Modules - Infrastructure as Code

> **Purpose**: This directory contains reusable Terraform modules for **Azure infrastructure deployment**.  
> **Modules help** in organizing Terraform code into **reusable components** for better maintainability and scalability.

---

## 📂 Available Modules

### 📌 [AKS Module](./Aks/README.md)
- **Provisions an Azure Kubernetes Service (AKS) cluster**.
- Configurable **node count, networking, RBAC, and monitoring**.
- Uses **Managed Identity** for secure access control.

### 🔑 [Service Principal Module](./ServicePrincipal/README.md)
- **Creates an Azure Service Principal** for authentication and role-based access control (RBAC).
- Useful for **CI/CD pipelines and automation**.
- Outputs **client ID, secret, and tenant ID**.

### 🏦 [Key Vault Module](./KeyVault/README.md)
- **Deploys an Azure Key Vault** for secure secrets management.
- Supports **Access Policies and RBAC**.
- Stores sensitive information such as API keys, passwords, and certificates.

---

## 🚀 How to Use a Module

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
4️⃣ **Destroy infrastructure when no longer needed**
```sh
terraform destroy
```

---

## ✅ Best Practices
✔ Use **remote state storage** to avoid state conflicts.
✔ Store sensitive data in **Azure Key Vault**, not in `terraform.tfvars`.
✔ Follow **modular design** for scalability.
✔ Run `terraform fmt` before committing changes.
✔ Implement `terraform validate` to check for errors.

---

🔗 **References**
- [Terraform Azure Provider](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs)
- [Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/)
- [Terraform Best Practices](https://learn.hashicorp.com/terraform)

---

💡 *Maintained by [Your Name]*
