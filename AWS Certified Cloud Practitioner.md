1️⃣ AWS Global Infrastructure 
       Region → Geographic area (e.g., eu-west-1)
       Availability Zone (AZ) → One or more data centers in a Region
       Edge Location → Used for CDN (CloudFront, Global Accelerator)
       High availability = Multi-AZ
       Disaster recovery = Multi-Region

2️⃣ Shared Responsibility Model (Critical)
       1.AWS = Security of the Cloud
           -Physical hardware
           -Networking infrastructure
           -Hypervisor
           -Managed service patching (RDS engine, etc.)
       2.Customer = Security in the Cloud
           -IAM policies
           -Data encryption settings
           -Guest OS patching (EC2)
           -Security groups
       If it's EC2 → YOU patch OS
       If it's RDS → AWS patches engine
3️⃣ Core Compute Services
       | Service           | When Used                       |
       | ----------------- | ------------------------------- |
       | EC2               | Virtual servers                 |
       | Lambda            | Serverless event-driven compute |
       | ECS               | Containers                      |
       | Fargate           | Serverless containers           |
       | Elastic Beanstalk | PaaS deployment                 |
       | Auto Scaling      | Adjust capacity automatically   |
       
       Elasticity = Scale up/down
       Scalability = Handle growth
4️⃣ Storage 
       | Storage Type | Used For             |
       | ------------ | -------------------- |
       | S3           | Object storage       |
       | EBS          | Block storage (EC2)  |
       | EFS          | Linux file storage   |
       | FSx          | Windows file systems |
       | Glacier      | Archive              |

       S3 Storage Classes:
          S3 Standard     → Frequent access
          S3 Standard-IA  → Infrequent
          One Zone-IA     → Cheaper, single AZ
          Glacier Flexible → Minutes to hours retrieval
          Deep Archive → 12+ hours retrieval
          Intelligent-Tiering → Automatic movement
      Exam trick:
          “Automatic tiering” → Intelligent-Tiering 
          
5️⃣ Database
      | Service  | Type                        |
      | -------- | --------------------------- |
      | RDS      | Relational                  |
      | Aurora   | High-performance relational |
      | DynamoDB | NoSQL                       |
      | Redshift | Data warehouse              |

      | DMS      | Database migration          |
6️⃣ Networking Essentials
      VPC = Isolated virtual network
      Security Group = Instance-level firewall (stateful)
      NACL = Subnet-level firewall (stateless)
      Route 53 = DNS
      ELB = Distributes traffic across AZs
      CloudFront = CDN(Content Delivery Network)
      Global Accelerator = Low latency via AWS backbone
      Security Group → allow rules only
      NACL → allow + deny rules
