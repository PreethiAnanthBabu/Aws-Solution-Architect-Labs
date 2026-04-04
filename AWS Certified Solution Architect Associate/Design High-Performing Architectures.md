# Storage choices
💾 1. Static Content → S3 + CloudFront
✅ Use:
     Amazon S3
     Amazon CloudFront
💡 Why?
     S3 stores static files (images, JS, HTML)
     CloudFront:
         Caches content globally
         Reduces latency
🧠 Exam Clues:
    “Static website”
    “Global low latency delivery”
👉 Answer = S3 + CloudFront

📂 2. Shared File System → EFS
✅ Use:
     Amazon EFS
💡 Why?
     Shared across multiple EC2 instances
     POSIX-compliant (like Linux file system)
🧠 Exam Clues:
    “Shared file system”
    “Multiple instances access same files”
👉 Answer = EFS

⚡ 3. Low-Latency Block Storage → EBS
✅ Use:
     Amazon EBS
💡 Why?
     High performance
     Attached to a single EC2 instance
🧠 Exam Clues:
    “Database storage”
    “Low latency / high IOPS”
👉 Answer = EBS

📊 4. Big Data Analytics → S3 + Athena / Glue
✅ Use:
     Amazon S3
     Amazon Athena
     AWS Glue
💡 Why?
     S3 = data lake
     Athena = SQL queries on S3
     Glue = data catalog + ETL
🧠 Exam Clues:
    “Query data without loading”
    “Serverless analytics”
👉 Answer = S3 + Athena / Glue

⚠️ TRAP: Millions of Small Files + High Throughput
❗ Question Pattern:
    “Millions of small objects”
    “High throughput / scalable storage”
✅ Correct Answer:
👉 S3
❌ Wrong:
EFS
💡 Why?
     S3:
        Scales massively
        Handles billions of objects
     EFS:
        Better for shared file systems
        Not optimized for massive object workloads

| Scenario                | Answer             |
| ----------------------- | ------------------ |
| Static content delivery | S3 + CloudFront    |
| Shared file system      | EFS                |
| Low-latency storage     | EBS                |
| Big data analytics      | S3 + Athena / Glue |
| Millions of small files | S3                 |

# Compute Optimization
🖥️ 1. Event-Driven Compute → Lambda
✅ Use:
     AWS Lambda
💡 Why?
    Runs code only when triggered
    No servers to manage
    Scales automatically
🧠 Exam Clues:
   “Event-driven”
   “No infrastructure management”
   “Run code in response to events”
👉 Answer = Lambda

📦 2. Containers → ECS / EKS
✅ Use:
     Amazon ECS
     Amazon EKS
💡 Differences:
     Service Use Case
          ECS	Simpler, AWS-native
          EKS	Kubernetes-based
💡 Why?
     Package apps with dependencies
     Portable and scalable
🧠 Exam Clues:
    “Containerized application”
    “Microservices architecture”
    “Kubernetes”
👉 Answer = ECS or EKS

📈 3. Auto Scaling → Dynamic Scaling
✅ Use:
     Amazon EC2 Auto Scaling
💡 Types:
     Dynamic scaling → based on metrics (CPU, requests)
     Scheduled scaling → known patterns
💡 Why?
     Automatically adjusts capacity
     Cost-efficient + highly available
🧠 Exam Clues:
    “Scale based on demand”
    “Maintain performance under load”
👉 Answer = Auto Scaling

🧮 4. Batch Processing → AWS Batch
✅ Use:
     AWS Batch
💡 Why?
     Runs large-scale batch jobs
     Automatically provisions compute
🧠 Exam Clues:
    “Batch workloads”
    “Queue jobs and process later”
👉 Answer = AWS Batch

| Scenario             | Answer                |
| -------------------- | --------------------- |
| Event-driven compute | Lambda                |
| Containers           | ECS / EKS             |
| Auto scaling         | EC2 Auto Scaling      |
| Batch jobs           | AWS Batch             |
| Unpredictable spikes | Lambda / Auto Scaling |

# Database Performance
🗄️ 1. Read-Heavy Workloads → Read Replicas (RDS)
✅ Use:
     Amazon RDS Read Replicas
💡 Why?
     Offload read traffic from primary DB
     Scale horizontally for reads
🧠 Exam Clues:
    “High read traffic”
    “Improve read performance”
👉 Answer = Read Replicas

⚡ 2. Write-Heavy Workloads → DynamoDB
✅ Use:
     Amazon DynamoDB
💡 Why?
     Handles massive write throughput
     Fully managed + auto scaling
⚠️ Important:
👉 Partition key design matters
     Good key → Even load → Fast ⚡
     Bad key → Hot partition → Throttle(rejecting the request) 🚫
🧠 Exam Clues:
    “High write throughput”
    “Massive scale / NoSQL”
👉 Answer = DynamoDB

🚀 3. Caching → ElastiCache
✅ Use:
     Amazon ElastiCache
     Redis
     Memcached
💡 Why?
     Reduces DB load
     Speeds up response time
🧠 Exam Clues:
    “Reduce latency”
    “Cache frequently accessed data”
👉 Answer = ElastiCache

📊 4. Analytics → Redshift
✅ Use:
     Amazon Redshift
💡 Why?
     Optimized for:
     OLAP (analytics queries)
     Large datasets
🧠 Exam Clues:
    “Data warehouse”
    “Complex queries / BI tools”
👉 Answer = Redshift

⚠️ TRAP: Sub-Millisecond Latency
❗ Question Pattern:
    “Ultra-low latency”
    “Sub-millisecond response time”
✅ Correct Answers:
👉 DynamoDB + DAX
👉 OR Redis (ElastiCache)
💡 Why?
   🔹 DynamoDB + DAX:
        DAX = DynamoDB Accelerator (in-memory cache)
        Microsecond latency
   🔹 Redis:
        In-memory data store
        Extremely fast reads/writes
❌ Wrong Answers:
     RDS (too slow for sub-ms)
     Redshift (analytics, not low-latency)

| Scenario       | Answer                 |
| -------------- | ---------------------- |
| Read-heavy DB  | RDS Read Replicas      |
| Write-heavy DB | DynamoDB               |
| Caching        | ElastiCache            |
| Analytics      | Redshift               |
| Sub-ms latency | DynamoDB + DAX / Redis |

# Networking & Edge
🌍 1. Global Users → CloudFront + Edge Locations
✅ Use:
     Amazon CloudFront
     Edge Locations
💡 Why?
     Content cached closer to users globally
     Reduces latency dramatically
🧠 Exam Clues:
    “Users worldwide”
    “Low latency content delivery”
    “Static or dynamic content acceleration”
👉 Answer = CloudFront

🔗 2. Hybrid Cloud → Direct Connect / VPN
✅ Use:
     AWS Direct Connect
     AWS VPN
💡 Differences:
     Service	                         Use Case
      VPN	                       Quick setup, over internet
      Direct Connect	             Dedicated, stable, high bandwidth
🧠 Exam Clues:
    “On-premises to AWS”
    “Hybrid architecture”
👉 Answer = VPN or Direct Connect

⚖️ 3. Load Balancing → ALB vs NLB vs GWLB
✅ Use:
     Application Load Balancer
     Network Load Balancer
     Gateway Load Balancer
💡 Comparison:
     Load Balancer	     Layer	                  Use Case
       ALB         L7 (HTTP/HTTPS)	             Web apps, routing
       NLB	    L4 (TCP/UDP)	             High performance, static IP
       GWLB	    L3/L4	                       Security appliances
🧠 Exam Clues:
    “HTTP/HTTPS routing” → ALB
    “Ultra high performance / TCP” → NLB
    “Firewall / inspection” → GWLB

| Scenario                | Answer               |
| ----------------------- | -------------------- |
| Global content delivery | CloudFront           |
| Hybrid cloud            | VPN / Direct Connect |
| HTTP load balancing     | ALB                  |
| TCP / static IP         | NLB                  |
| Appliance routing       | GWLB                 |

# Data Pipelines
🔄 1. Streaming Data → Kinesis
✅ Use:
     Amazon Kinesis Data Streams
     Amazon Kinesis Data Firehose
💡 Differences:
     Service	        Use Case
     Data Streams	     Real-time processing (custom apps)
Firehose	Load to S3/Redshift/OpenSearch (managed)
💡 Why?
Handles continuous, real-time data
Scales automatically
🧠 Exam Clues:
“Streaming data”
“Real-time ingestion”

👉 Answer = Kinesis
