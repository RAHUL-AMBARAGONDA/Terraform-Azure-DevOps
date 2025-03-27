# 🚀 Terraform Pipelines - Infrastructure Deployment

> **Purpose**: Automate the deployment and destruction of infrastructure resources using **CI/CD pipelines**.

---

## 📂 Directory Structure

```
Pipelines/
│── create.yaml   # 🚀 CI/CD pipeline for infrastructure creation
│── destroy.yaml  # 🔥 CI/CD pipeline for infrastructure destruction
```

---

## 📄 File Descriptions

### 🚀 `create.yaml`
- Defines the **CI/CD pipeline** for creating infrastructure using Terraform.
- Executes Terraform commands in a structured manner.
- Example workflow:
  ```yaml
  steps:
    - name: Checkout code
      uses: actions/checkout@v3
    
    - name: Terraform Init
      run: terraform init
    
    - name: Terraform Plan
      run: terraform plan
    
    - name: Terraform Apply
      run: terraform apply -auto-approve
  ```
- Ensures a **repeatable, automated deployment** process.

### 🔥 `destroy.yaml`
- Automates **infrastructure teardown** when no longer needed.
- Example workflow:
  ```yaml
  steps:
    - name: Checkout code
      uses: actions/checkout@v3
    
    - name: Terraform Init
      run: terraform init
    
    - name: Terraform Destroy
      run: terraform destroy -auto-approve
  ```
- Helps in **cost management** and keeping environments clean.

---

## ✅ Best Practices
✔ Use **separate workflows** for creation and destruction to avoid accidental deletions.  
✔ Implement **approval mechanisms** in CI/CD pipelines for production environments.  
✔ Store **Terraform state remotely** to enable team collaboration.  
✔ Use **secrets management** for sensitive data like API keys and credentials.  

---

🔗 **References**
- [GitHub Actions for Terraform](https://github.com/hashicorp/setup-terraform)
- [Best Practices for CI/CD Pipelines](https://learn.microsoft.com/en-us/devops/pipelines/best-practices)
