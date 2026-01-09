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
		 
# Advantages:
     1.Cost Efficiency
         -No upfront hardware cost
         -Pay only for what you use
         -Reduced maintenance and data center costs
         👉 AWS example: Pay per second for EC2, pay per request in Lambda
	 2.High Availability & Reliability
         -Applications run across multiple Availability Zones
         -Built-in fault tolerance
         👉 AWS example: ALB + Multi-AZ RDS
	 3.Scalability & Elasticity
         -Scale resources up or down automatically
         -Handle traffic spikes easily
		 -Vertical scaling
		      Increase or decrease the capacity of a single server (CPU, RAM, storage).
              Think of it as “making a single instance stronger or weaker.”
		 -Horizontal scaling
		      Add or remove more servers/instances to handle load.
              Think of it as “adding more machines to share the workload.”
         👉 AWS example: Auto Scaling, AWS Lambda
	4.Speed & Agility
        -Launch servers and services in minutes
        -Faster development and deployment
        👉 AWS example: CloudFormation, Elastic Beanstalk
	5.Global Reach
        -Deploy applications in multiple AWS Regions worldwide
        -Low latency for users
        👉 AWS example: CloudFront, Route 53
	6.Security
        -Strong physical and network security
        -Advanced encryption and access control
        👉 AWS example: IAM, KMS, Shield, WAF
	7.Automatic Maintenance
        -AWS manages hardware, power, cooling
        -Managed services reduce operational overhead
        👉 AWS example: RDS handles backups and patching
	8.Disaster Recovery & Backup
        -Easy backups and replication
        -Faster recovery from failures
        👉 AWS example: S3 versioning, cross-region replication    
	9.Innovation & Flexibility
        -Access to latest technologies (AI, ML, analytics)
        -Try new ideas without big investments
        👉 AWS example: SageMaker, Bedrock
     
