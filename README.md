# Terraform AWS Project 4: CI/CD with GitHub Actions

## Objective

Build a CI/CD pipeline for Terraform using GitHub Actions to automate infrastructure validation and planning.

This project demonstrates modern DevOps practices by integrating Infrastructure as Code (IaC) with automated workflows.

## Technologies Used

* Terraform
* AWS
* GitHub Actions
* Git
* GitHub
* YAML

## Project Architecture

Developer
↓
Git Push
↓
GitHub Repository
↓
GitHub Actions Workflow
↓
Terraform Format Check
↓
Terraform Init
↓
Terraform Validate
↓
Terraform Plan
↓
AWS Infrastructure

## CI/CD Workflow

The GitHub Actions pipeline automatically runs whenever code is pushed to the repository or a pull request is created.

Pipeline Stages:

1. Checkout Repository
2. Setup Terraform
3. Configure AWS Credentials
4. Terraform Format Validation
5. Terraform Initialization
6. Terraform Configuration Validation
7. Terraform Plan Generation

## Security

AWS credentials are stored securely using GitHub Repository Secrets.

Secrets Used:

* AWS_ACCESS_KEY_ID
* AWS_SECRET_ACCESS_KEY

No credentials are stored inside the repository.

## Problems Encountered and Resolutions

### GitHub Secrets Configuration

Issue:
GitHub Actions could not authenticate to AWS.

Resolution:
Configured repository secrets and verified workflow credential configuration.

### Terraform Configuration Not Found

Issue:
Workflow failed with "No configuration files" error.

Resolution:
Moved Terraform files from `.github/workflows` to the repository root and kept only `terraform.yml` inside the workflow directory.

### Git Repository Cleanup

Issue:
Terraform provider binaries exceeded GitHub file size limits.

Resolution:
Implemented `.gitignore` to exclude:

* .terraform/
* terraform.tfstate
* terraform.tfstate.backup
* terraform.tfvars

## Skills Demonstrated

* Infrastructure as Code
* Terraform
* GitHub Actions
* CI/CD Pipelines
* AWS Authentication
* Git Version Control
* Cloud Automation
* DevOps Practices
* Troubleshooting and Debugging

## Future Improvements

* Automated Terraform Apply
* Manual Approval Gates
* Remote Terraform State
* Environment Separation (Dev/Test/Prod)
* Terraform Workspaces
* OIDC Authentication instead of Access Keys

## Lessons Learned

* CI/CD pipelines improve deployment consistency
* GitHub Actions integrates effectively with Terraform
* Repository structure is critical for automation
* Secrets management is essential for secure cloud operations
* Infrastructure validation should be automated before deployment
