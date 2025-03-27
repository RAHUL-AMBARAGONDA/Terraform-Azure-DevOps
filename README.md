# Azure DevOps End-to-End Project with Terraform 🚀

## Overview
This project provides a professional, real-world implementation of provisioning an **Azure Kubernetes Service (AKS) cluster** for multiple environments using **Terraform** and **Azure DevOps**. It follows best practices in infrastructure automation, CI/CD pipeline structuring, **Git branching strategies**, and **resource management** to ensure a **scalable, maintainable, and secure** cloud infrastructure.

## Table of Contents 📌
- [Prerequisites](#prerequisites)
- [Project Structure](#project-structure)
- [Setup Guide](#setup-guide)
- [CI/CD Pipeline Stages](#ci-cd-pipeline-stages)
- [Branching Strategy](#branching-strategy)
- [Resource Management](#resource-management)
- [Cleanup](#cleanup)
- [Contributing](#contributing)
- [License](#license)

---

## Prerequisites ✅
Before starting, ensure you have the following installed and configured:

1. **Azure Account** – A valid **Azure Subscription** ([Sign up](https://azure.microsoft.com/free/)).
2. **Terraform** – Install [Terraform](https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli).
3. **Azure DevOps Account** – Create an account at [Azure DevOps](https://dev.azure.com/).
4. **Git** – Install [Git](https://git-scm.com/downloads) for version control.
5. **Azure CLI** – Install [Azure CLI](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli) to interact with Azure services.
6. **Kubectl** – Install [kubectl](https://kubernetes.io/docs/tasks/tools/) for Kubernetes management.

---

## Project Structure 📁
The project follows a modular architecture to ensure **reusability, scalability, and easy management**.

```bash
.
├── environments
│   ├── dev
│   │   ├── main.tf
│   │   ├── variables.tf
│   │   └── backend.tf
│   ├── stage
│   │   ├── main.tf
│   │   ├── variables.tf
│   │   └── backend.tf
│   └── prod
│       ├── main.tf
│       ├── variables.tf
│       └── backend.tf
├── modules
│   ├── aks
│   │   ├── main.tf
│   │   ├── variables.tf
│   │   └── outputs.tf
│   ├── keyvault
│   │   ├── main.tf
│   │   ├── variables.tf
│   │   └── outputs.tf
│   └── service-principal
│       ├── main.tf
│       ├── variables.tf
│       └── outputs.tf
├── pipelines
│   ├── azure-pipelines.yml
│   ├── destroy-pipeline.yml
│   └── tests.yml
├── scripts
│   ├── setup.sh
│   ├── deploy.sh
│   ├── destroy.sh
│   └── validate.sh
└── README.md
```

---

## Setup Guide ⚙️
### 1️⃣ Clone the Repository 🖥️
```bash
git clone <repository-url>
cd azure-terraform-aks
```

### 2️⃣ Authenticate with Azure 🔑
```bash
az login
```

### 3️⃣ Initialize Terraform 🌍
```bash
cd environments/dev
terraform init
```

### 4️⃣ Apply Terraform Configuration ⚒️
```bash
terraform apply -auto-approve
```

### 5️⃣ Set Up CI/CD Pipeline 🚀
1. Navigate to **Azure DevOps**.
2. Create a **New Pipeline** and select **YAML Configuration**.
3. Link the repository and use `pipelines/azure-pipelines.yml`.
4. Trigger the first deployment.

---

## CI/CD Pipeline Stages 🔄
The CI/CD process ensures **automated, error-free, and scalable deployment** across multiple environments.

### 1️⃣ Validate 🔍
- Runs **Terraform format** and **validation checks**.

### 2️⃣ Dev Deploy 🏗️
- Deploys AKS cluster in **Development Environment**.

### 3️⃣ Stage Deploy 🚀
- Deploys AKS cluster in **Staging Environment** after successful **Dev Deployment**.

### 4️⃣ Destroy ❌
- Runs cleanup for **unused resources**.

---

## Branching Strategy 🌿
The project follows **Feature Branching Strategy** to ensure **code quality and collaboration**.

- **`main` branch** – Stable production-ready code.
- **`develop` branch** – Active development.
- **Feature branches (`feature/<name>`)** – For new features.
- **Bugfix branches (`bugfix/<name>`)** – For fixing issues.

### Git Workflow
```bash
git checkout -b feature/new-feature
# Make changes, commit, and push
git push origin feature/new-feature
# Create a Pull Request to `develop` branch
```

---

## Resource Management 🛠️
1. **Terraform State Management** 📜
   - Each environment has a **dedicated state file** stored securely in Azure Storage.
   
2. **Azure Key Vault** 🔐
   - Stores sensitive information (**Service Principal secrets, SSH Keys, etc.**).

3. **RBAC & IAM Permissions** 🔑
   - Service Principal requires **Contributor** and **Key Vault Admin** roles.

---

## Cleanup 🧹
To **destroy resources**, run:
```bash
cd environments/dev
terraform destroy -auto-approve
```
Or trigger **destroy-pipeline.yml** in Azure DevOps.

---

## Contributing 🤝
We welcome contributions! 🚀
1. Fork the repository 🍴
2. Create a new branch 🌿
3. Make your changes and commit ✅
4. Submit a Pull Request 📩

---

## License 📜
This project is licensed under the **MIT License**. See the **LICENSE** file for details.

---

🚀 **Happy Coding!**
