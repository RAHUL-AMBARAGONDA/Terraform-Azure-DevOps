# 🚀 Azure DevOps End-to-End Project with Terraform

## 📌 Overview
This project demonstrates the provisioning of an **Azure Kubernetes Service (AKS)** cluster for multiple environments using **Terraform** and **Azure DevOps**. It includes setting up a **CI/CD pipeline**, implementing **Git branching strategies**, and managing resources efficiently.

---

## 📖 Table of Contents

- 📋 [Prerequisites](#prerequisites)
- 🏗 [Project Structure](#project-structure)
- 🚀 [Getting Started](#getting-started)
- 🔄 [Pipeline Stages](#pipeline-stages)
- 🌿 [Branching Strategy](#branching-strategy)
- 📦 [Resource Management](#resource-management)
- 🧹 [Cleanup](#cleanup)
- 🤝 [Contributing](#contributing)
- 📜 [License](#license)

---

## 📋 Prerequisites
Ensure you have the following before starting:
- 🔹 **Azure Account**: Active Azure subscription.
- 🔹 **Terraform**: Installed on your local machine.
- 🔹 **Azure DevOps Account**: Sign up if you don’t have one.
- 🔹 **Git**: Installed for version control.

---

## 🏗 Project Structure

```
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

### 1️⃣ Clone the Repository:
```bash
git clone <repository-url>
cd Day 26
```

### 2️⃣ Set Up Azure Environment:
```bash
az login
```

### 3️⃣ Run the Prerequisite Script:
```bash
./scripts/prerequisite.sh
```

### 4️⃣ Deploy the Infrastructure:
Trigger the pipeline in **Azure DevOps** to provision resources.

---

## 🔄 Pipeline Stages
The **CI/CD pipeline** includes the following stages:

1. ✅ **Validate** - Runs Terraform validation.
2. 🚀 **Dev Deploy** - Provisions resources in the development environment.
3. 🏗 **Stage Deploy** - Provisions resources in the staging environment.
4. 🧹 **Destroy** - Cleans up resources after testing.

---

## 🌿 Branching Strategy
- **Feature Branching**: Work on new features in separate branches.
- **Pull Requests**: Merge changes into the main branch after code review.

---

## 📦 Resource Management
- **Terraform State Files**: Separate state files for each environment to prevent accidental modifications.
- **Azure Key Vault**: Securely store sensitive information.

---

## 🧹 Cleanup
To destroy resources, run the **cleanup pipeline**:

1. Select the environment (**Dev** or **Staging**) to destroy.
2. Confirm the destruction of resources.

---

## 🤝 Contributing
Contributions are welcome! 🚀 Please fork the repository and submit a pull request with your changes.

---

## 📜 License
This project is licensed under the **MIT License**. See the [LICENSE](LICENSE) file for details.

---

### 📺 Watch the YouTube Tutorial 🎥
For a detailed walkthrough, refer to the [YouTube Tutorial]() by **Tech Tutorials with Piyush**. Happy learning! 😊
