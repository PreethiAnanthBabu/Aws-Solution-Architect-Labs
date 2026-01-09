# AWS Cloud computing:
     Is the on-demand delivery of AWS computing resources—such as servers, storage, databases, networking, and software—over the internet, with pay-as-you-go pricing, instead of owning and maintaining physical data centers.In AWS,this means you use AWS data centers to run your applications rather than building your own infrastructure.

# Cloud Service Models:
     Cloud service models in AWS are IaaS, PaaS, and SaaS, which define how much responsibility is managed by AWS versus the customer.
     | Layer        | IaaS | PaaS | SaaS |
     | ------------ | ---- | ---- | ---- |
     | Applications | You  | You  | AWS  |
     | Data         | You  | You  | AWS  |
     | Runtime      | You  | AWS  | AWS  |
     | OS           | You  | AWS  | AWS  |
     | Servers      | AWS  | AWS  | AWS  |
     | Data Center  | AWS  | AWS  | AWS  |

# Cloud Deployment Models:
     Cloud deployment models describe where your cloud infrastructure runs and how it’s connected.
     1.Public Cloud- Your applications and data run on AWS infrastructure, shared securely with other customers.
       How it works in AWS
         -Runs in AWS Regions and Availability Zones
         -Uses shared physical hardware
         -Isolation is done using VPC, IAM, and security controls
         -You do not own or manage the hardware
       AWS Examples
         -EC2 instances in a VPC
         -S3 bucket
	    -RDS databases
       Key characteristics
         -Pay-as-you-go
         -Easy to scale up/down
	    -No hardware management
	    -High availability
       Best for
         -Websites & mobile apps
         -Startups and enterprises
         -Dev/Test environments
	2.Private Cloud- Private cloud provides exclusive, dedicated infrastructure for a single organization.
	  How it works in AWS
	    -Resources are dedicated, not shared
	    -Can be:
             On-premises private cloud
             AWS-hosted private cloud
	  AWS Ways to Build Private Cloud
         -Dedicated Hosts – physical servers for one customer
	    -Dedicated Instances – EC2 on dedicated hardware
	    -AWS Outposts – AWS services on-premises
       Key characteristics
         -More control and isolation
	    -Better for compliance
	    -Higher cost
	    -Less elastic than public cloud
	  Best for
         -Banking & healthcare
         -Regulatory workloads
         -Legacy applications
	3.Hybrid Cloud- Part of your system runs on-premises, and part runs on AWS.
       How it works in AWS
         -On-prem ↔ AWS connected via:
         -VPN
         -Direct Connect
       Example
         -Database on-prem
         -Application servers on AWS
       Best for
         -Gradual migration to AWS
         -Disaster recovery
         -Compliance requirements
	4.Multi Cloud- Using more than one cloud providers
       How it works
         -AWS + Azure + GCP
         -Managed via orchestration or containers
       Example
         -App hosted on AWS
         -Backup or analytics on Azure
       Best for
         -Vendor lock-in avoidance
         -Global redundancy
     
