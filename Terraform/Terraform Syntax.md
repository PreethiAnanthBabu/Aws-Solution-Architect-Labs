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
        
