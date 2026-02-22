# Terraform:
     Terraform is an open-source Infrastructure as Code (IaC) tool created by HashiCorp.
     It allows you to define and provision cloud infrastructure — including AWS resources — using simple configuration files.
     Instead of manually creating resources in the AWS Console, you write code to create:
        -EC2 instances
        -VPCs
        -Subnets
        -IAM roles
        -RDS databases
        -Load balancers
        -S3 buckets And more
# How Terraform Works with AWS:
     Terraform interacts with AWS using the AWS Provider, which connects Terraform to AWS APIs.
# Basic Workflow:
     Write Code → Define infrastructure in .tf files
     terraform init → Initialize provider plugins
     terraform plan → See what will be created/changed
     terraform apply → Deploy infrastructure to AWS
# Terraform Core Concepts:
     1️⃣ Providers - Plugins that allow Terraform to work with platforms like:
            -Amazon Web Services
            -Microsoft Azure
            -Google Cloud Platform
     2️⃣ Resources - Infrastructure components like:
            -aws_instance
            -aws_vpc
            -aws_s3_bucket
     3️⃣ State File - Terraform keeps track of infrastructure in a file called: terraform.tfstate
         In AWS projects, state is usually stored remotely in:
            -S3
            -DynamoDB (for state locking)
     4️⃣ Modules - A Terraform module is just a reusable folder of Terraform code that you can call multiple times with                         different inputs.
         Types of Terraform Modules:
            -Root Module - The main directory where you run.Every Terraform project has one root module.
                           terraform init
                           terraform apply
            -Child Module - A module called by the root module.
                            Example:
                            module "vpc" {
                              source = "./modules/vpc"
                            }
