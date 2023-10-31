# Terraform
# Creating and Destroying an EC2 Instance with Terraform

This guide will walk you through the process of using Terraform to create and destroy an EC2 instance on Amazon Web Services (AWS).

# Prerequisites
Before you begin, ensure that you have the following:

AWS Account: Access to an AWS account with appropriate permissions to create and manage EC2 instances.

Terraform Installed: Install Terraform on your local machine. You can download it from Terraform's official website.

AWS Access Credentials: Obtain your AWS access key ID and secret access key. Ensure they have the necessary permissions. You can set these credentials in environment variables or use AWS CLI's configuration for authentication.

# Steps to Create an EC2 Instance
Clone Repository: Clone the repository or create a new directory for your Terraform configurations.

Configure AWS Provider: Create a .tf file to set up your AWS provider with the necessary credentials and region.

Write Terraform Configuration: defining the EC2 instance.

~~~
provider "aws" {
  region     = "your_aws_region"
  access_key = "your_access_key"
  secret_key = "your_secret_key"
}
resource "aws_instance" "example" {
  ami           = "ami-0c55b159cbfafe1f0" # Your desired AMI
  instance_type = "t2.micro"
  # Add other configurations like key_name, security_groups, etc.

}
~~~
Initialize Terraform: Run terraform init in your terminal to initialize Terraform and download necessary providers.
~~~
terraform init
~~~
Preview Changes: Execute terraform plan to see what resources Terraform will create.
~~~
terraform plan
~~~
Apply Changes: Run terraform apply and confirm the action to create the EC2 instance.
~~~
terraform apply
~~~
Destroy Resources: Run terraform destroy and confirm the action. This will remove the created EC2 instance.
~~~
terraform destroy
~~~
# Possible Errors and Troubleshooting
# Access Denied Errors

If you encounter "Access Denied" errors during resource creation or deletion, verify your AWS credentials and ensure they have the necessary permissions for EC2 operations.

# Terraform State Errors

If you face issues with Terraform state (e.g., if the instance was manually deleted), you might need to remove the state file or perform a terraform refresh to update the state.
