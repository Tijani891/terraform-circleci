# Terraform CircleCI Example

This repository provides an example of fully automating infrastructure deployment using Terraform with CircleCI. All Terraform processes, including initialization, planning, and applying changes, are handled by CircleCI.

## Prerequisites

Before you begin, ensure you have the following:

- A CircleCI account linked to your version control system (e.g., GitHub, Bitbucket).
- An account with your cloud provider (AWS, GCP, etc.).
- Required environment variables set up in CircleCI (e.g., `AWS_ACCESS_KEY_ID`, `AWS_SECRET_ACCESS_KEY`).

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

## How It Works

This project is configured to automate the entire Terraform workflow through CircleCI. The following steps are performed automatically by the CircleCI pipeline:

1. **Terraform Initialization**: Initializes the Terraform working directory.
2. **Terraform Validation**: Validates the Terraform configuration files.
3. **Terraform Plan**: Creates an execution plan to preview changes without making any.
4. **Terraform Apply**: Applies the changes required to reach the desired state of the configuration.
5. **Terraform Destroy**: Optionally destroys the infrastructure when needed.

### Setting Up CircleCI

1. **Add the repository to CircleCI**:
   - Go to the CircleCI dashboard and add this repository.

2. **Configure Environment Variables**:
   - Set the required environment variables in the CircleCI project settings (e.g., `AWS_ACCESS_KEY_ID`, `AWS_SECRET_ACCESS_KEY`, `TF_VAR_region`, etc.).

3. **Trigger a Pipeline**:
   - Push any change to the repository to trigger the CircleCI pipeline. The pipeline will handle all Terraform operations automatically.

## Customization

You can customize the CircleCI configuration (`.circleci/config.yml`) to suit your needs, such as:

- Adjusting the Terraform commands and arguments.
- Modifying the workflow to include additional steps like linting, testing, or notifications.

## Contributions

Contributions are welcome! Feel free to open an issue or submit a pull request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

