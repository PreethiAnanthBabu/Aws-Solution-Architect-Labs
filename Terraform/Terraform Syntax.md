# Blocks: the big containers
     A block looks like:
        
        block_type "name" "label" {
        key = value
        }
        
     Examples of block types you used:
        -provider
        -resource
        -variable
        -output
        -data
        -locals
        -module
# Provider block (connect to AWS)
     Terraform, talk to AWS in particular region
        
        provider "aws" {
        region = "us-east-1"
        }
        
# Resource block
     Create a VPC. I will call it "this" inside Terraform
     aws_vpc = the AWS resource type
     this = Terraform’s nickname (you choose it)
        
        resource "aws_vpc" "this" {
        cidr_block = "10.0.0.0/16"
        }
# key = value lines
     Inside blocks you set properties:
     left side cidr_block = setting name
     right side "10.0.0.0/16" = value (string)

        cidr_block = "10.0.0.0/16"

# Data types (strings, numbers, lists, maps)   
     1.String
        name = "ire-3tier"
     2.Number 
        count = 2
     3.Boolean
        multi_az = true
     4.List (array) 
        azs = ["us-east-1a", "us-east-1b"]
     5.Map (dictionary)
        tags = {
        Project = "ire-3tier"
        Env     = "dev"
        }

# Variables  
     Use the value provided by the user.They are values that someone running Terraform can change.So variables make your          Terraform flexible and reusable 
        
        variable "region" {
        type = string
        }

     Used like:
        
        region = var.region 

# Locals 
     Think of locals as internal helper values.They are calculated inside Terraform and cannot be changed by the user.

        locals {
        project_name = "three-tier-app"
        }

     Used like:
     
        Name = local.project_name

     Use Variables When - User should change the value.Environment differences exist
        Examples:
           -region
           -instance type
           -VPC CIDR
           -DB password
     Use Locals When - Value is calculated.Value repeats many times.Value depends on variables
        Examples:
           -subnet CIDR calculations
           -naming conventions
           -common tags  

# Count
     count tells Terraform to create multiple copies of a resource automatically.
     Without count, you must write resources manually.
        
        resource "aws_subnet" "public" {
        count = 2
        }
        
     Terraform creates:  
     
        aws_subnet.public[0]
        aws_subnet.public[1]  

# Output
     Outputs show results after apply.

        output "alb_dns_name" {
        value = aws_lb.app_alb.dns_name
        }

# Plan and apply
     terraform init → download provider/plugins
     terraform fmt → format files
     terraform validate → syntax check
     terraform plan → preview
     terraform apply → create
     terraform destroy → remove        
