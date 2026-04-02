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
