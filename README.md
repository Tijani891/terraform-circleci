# Terraform CircleCI Example

This repository provides a simple example of using Terraform with CircleCI to automate infrastructure deployment. It demonstrates how to create, manage, and destroy infrastructure using Terraform, with continuous integration and deployment managed by CircleCI.

## Prerequisites

Before you begin, ensure you have the following installed:

- [Terraform](https://www.terraform.io/downloads.html) (v0.12 or later)
- [CircleCI CLI](https://circleci.com/docs/2.0/local-cli/) (optional for local testing)
- An account with your cloud provider (AWS, GCP, etc.)
- Access to a CircleCI account

## Project Structure

```
.
├── .circleci
│   └── config.yml           # CircleCI pipeline configuration file
├── main.tf                  # Main Terraform configuration file
├── variables.tf             # Terraform variables definition
├── outputs.tf               # Terraform outputs definition
├── README.md                # Project documentation
└── .gitignore               # Files to be ignored by Git
```

## Setup and Configuration

### 1. Clone the Repository

```sh
git clone https://github.com/Tijani891/terraform-circleci.git
cd terraform-circleci
```

### 2. Configure Terraform Variables

Edit the `variables.tf` file to set the necessary variables for your cloud provider. Alternatively, you can set these variables through environment variables or a `terraform.tfvars` file.

### 3. Initialize Terraform

Initialize the Terraform working directory:

```sh
terraform init
```

### 4. Plan the Infrastructure

Review the infrastructure changes that Terraform will make:

```sh
terraform plan
```

### 5. Apply the Infrastructure

Deploy the infrastructure:

```sh
terraform apply
```

### 6. Destroy the Infrastructure

When you're done, you can destroy the infrastructure to avoid unnecessary costs:

```sh
terraform destroy
```

## CircleCI Integration

This project includes a CircleCI configuration file (`.circleci/config.yml`) that automates the Terraform workflow. The pipeline includes steps for:

- Validating the Terraform configuration
- Planning the infrastructure changes
- Applying the changes in a production environment

### Setting Up CircleCI

1. **Add the repository to CircleCI**:
   - Go to the CircleCI dashboard and add this repository.

2. **Set environment variables**:
   - Set the required environment variables in CircleCI (e.g., `AWS_ACCESS_KEY_ID`, `AWS_SECRET_ACCESS_KEY`, `TF_VAR_region`, etc.)

3. **Trigger a build**:
   - Push your changes to the repository to trigger the CircleCI pipeline.

## Contributions

Contributions are welcome! Feel free to open an issue or submit a pull request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
