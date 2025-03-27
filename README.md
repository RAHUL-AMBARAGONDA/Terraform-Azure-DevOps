# Azure DevOps End-to-End Project with Terraform 

![Azure](https://img.shields.io/badge/Azure-DevOps-blue.svg) ![Terraform](https://img.shields.io/badge/Terraform-IaC-purple.svg) ![CI/CD](https://img.shields.io/badge/CI%2FCD-Pipeline-green.svg)

## Overview
This project demonstrates the provisioning of an **Azure Kubernetes Service (AKS) cluster** for multiple environments using **Terraform and Azure DevOps**. It includes the creation of a **CI/CD pipeline**, **Git branching strategies**, and **resource management**.

---
## 📌 Table of Contents
- [Prerequisites](#prerequisites)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Pipeline Stages](#pipeline-stages)
- [Branching Strategy](#branching-strategy)
- [Resource Management](#resource-management)
- [Cleanup](#cleanup)
- [Contributing](#contributing)
- [License](#license)

---
## ⚙️ Prerequisites
Before running the project, ensure you have the following installed:
- ✅ **Azure Account**: An active Azure subscription.
- ✅ **Terraform**: Installed on your local machine.
- ✅ **Azure DevOps Account**: Sign up for Azure DevOps.
- ✅ **Git**: Installed for version control.

---
## 📁 Project Structure
```plaintext
.
├── Dev
│   ├── main.tf
│   └── variables.tf
├── Stage
│   ├── main.tf
│   └── variables.tf
├── Modules
│   ├── AKS
│   ├── ServicePrincipal
│   └── KeyVault
├── Pipelines
│   ├── azure-pipelines.yml
│   └── destroy-pipeline.yml
└── README.md
```

---
## 🚀 Getting Started
### Clone the Repository
```bash
git clone <repository-url>
cd <repository-folder>
```
### Log in to Azure
```bash
az login
```
### Run the Prerequisite Script
```bash
./scripts/prerequisite.sh
```
### Deploy the Infrastructure
Trigger the pipeline in **Azure DevOps** to provision resources.

---
## 🔄 CI/CD Pipeline Stages
The **CI/CD pipeline** follows these stages:
1. **Validate**: Runs Terraform validation.
2. **Dev Deploy**: Provisions resources in the **development** environment.
3. **Stage Deploy**: Provisions resources in the **staging** environment.
4. **Destroy**: Cleans up resources after testing.

---
## 🔀 Branching Strategy
- **Feature Branching**: Create a feature branch for each new feature or bug fix.
- **Pull Requests**: Merge changes back to the main branch after review.

---
## 🔐 Resource Management
- **Terraform State Files**: Each environment has a dedicated **state file** stored securely.
- **Azure Key Vault**: Used to store sensitive credentials securely.

---
## 🧹 Cleanup
To destroy resources, run the **cleanup pipeline**:
1. Select the environment (**Dev** or **Staging**) to destroy.
2. Confirm the destruction of resources.

---
## 🤝 Contributing
Contributions are welcome! Please **fork the repository**, make changes, and submit a **pull request**.

---
## 📜 License
This project is licensed under the **MIT License**. See the `LICENSE` file for details.

---
### ⭐ If you found this project useful, give it a star on GitHub!
