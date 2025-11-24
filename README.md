# Azure VMs Terraform Configuration

This Terraform configuration deploys Linux virtual machines on Azure.

## Prerequisites

- [Terraform](https://www.terraform.io/downloads.html) installed
- Azure CLI installed and configured
- SSH key pair generated (`~/.ssh/id_rsa.pub`)

## What This Creates

- Azure Resource Group
- Virtual Network and Subnet
- Network Interfaces
- 2 Linux VMs (Ubuntu 22.04 LTS)

## Terraform Commands

### Initialize Terraform
```bash
terraform init
```
Downloads required providers and initializes the working directory.

### Validate Configuration
```bash
terraform validate
```
Checks the configuration syntax.

### Plan Deployment
```bash
terraform plan
```
Shows what resources will be created/modified/destroyed.

### Apply Configuration
```bash
terraform apply
```
Creates the resources. Add `-auto-approve` to skip confirmation prompt.

### Show Current State
```bash
terraform show
```
Displays the current state of your infrastructure.

### List Resources
```bash
terraform state list
```
Lists all resources in the state file.

### Destroy Resources
```bash
terraform destroy
```
Removes all resources managed by this configuration. Add `-auto-approve` to skip confirmation.

## Variables

- `vm_count`: Number of VMs to create (default: 2)

To override:
```bash
terraform apply -var="vm_count=3"
```

## Configuration

Update `subscription_id` in `main.tf` with your Azure subscription ID before applying.
