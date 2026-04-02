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
