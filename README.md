# Example of GitHub Actions to exec terraform
This repo guide you to exec terraform commands to typical cloud services.

## AWS

### Steps
- Step1: Adding the identity provider to AWS
- Step2: Create IAM Role to assume
- Step3: Create a workflow

### Step1: Adding the identity provider to AWS
Before you start to use GitHub Actions with AWS, you have to add the GitHub OIDC provider to IAM.

This operation only need to be done once on your account. In this operation you must get thumbprint of GitHub. If you use Management Console (not cli), you can easily get it by only press a button. For this reason, I recommend you to use Management Console.

More detail
- [Creating OpenID Connect (OIDC) identity providers | AWS](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_providers_create_oidc.html)
- [Configuring OpenID Connect in Amazon Web Services | GitHub](https://docs.github.com/en/actions/deployment/security-hardening-your-deployments/configuring-openid-connect-in-amazon-web-services)

### Step2: Create IAM Role to assume
Add a role to assume from GitHub Actions.

See sample code in this repository.
[./terraform/aws/iam.tf](./terraform/aws/iam.tf)

### Step3: Create a workflow
See sample code in this repository.
[./.github/workflows/terraform-aws.yml](./.github/workflows/terraform-aws.yml)

Don't forget to add a secret, AWS_ROLE_TO_ASSUME, to repo.
