# Azure Resource Group - Terraform Configuration

This Terraform configuration creates an Azure resource group.

## Prerequisites

- [Terraform](https://www.terraform.io/downloads.html) installed (version 1.0+)
- Azure CLI installed and configured, or service principal credentials
- Appropriate Azure subscription permissions

## Authentication

You can authenticate to Azure using one of the following methods:

1. **Azure CLI** (Recommended for local development):
   ```bash
   az login
   ```

2. **Service Principal** (Recommended for CI/CD):
   ```bash
   export ARM_CLIENT_ID="your-client-id"
   export ARM_CLIENT_SECRET="your-client-secret"
   export ARM_SUBSCRIPTION_ID="your-subscription-id"
   export ARM_TENANT_ID="your-tenant-id"
   ```

## Usage

1. **Initialize Terraform**:
   ```bash
   terraform init
   ```

2. **Review the execution plan**:
   ```bash
   terraform plan
   ```

3. **Apply the configuration**:
   ```bash
   terraform apply
   ```

4. **Customize variables** (optional):
   - Copy `terraform.tfvars.example` to `terraform.tfvars`
   - Edit `terraform.tfvars` with your desired values
   - Run `terraform plan` and `terraform apply`

## Variables

- `resource_group_name` (string): The name of the resource group (default: "rg-example")
- `location` (string): The Azure region (default: "East US")
- `tags` (map): Tags to apply to the resource group (default: Environment=Development, Project=Example)

## Outputs

- `resource_group_name`: The name of the created resource group
- `resource_group_id`: The ID of the created resource group
- `resource_group_location`: The location of the created resource group

## Clean Up

To destroy the created resources:

```bash
terraform destroy
```
