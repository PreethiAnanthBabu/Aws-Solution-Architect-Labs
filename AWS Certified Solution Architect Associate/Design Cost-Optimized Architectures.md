# Compute Cost Optimization
💸 1. Steady Workloads → Reserved Instances / Savings Plans
✅ Use:
     Reserved Instances (RI)
     Savings Plans
💡 Why?
     Significant cost savings vs On-Demand
     Best for predictable, long-term usage
💡 Differences:
     Option	Flexibility
     Reserved Instances	Less flexible
     Savings Plans	More flexible
🧠 Exam Clues:
    “Steady / predictable workload”
👉 Answer = RI or Savings Plans

⚡ 2. Interruptible Workloads → Spot Instances
✅ Use:
     Amazon EC2 Spot Instances
💡 Why?
     Up to ~90% cheaper
     Can be terminated anytime by AWS
🧠 Exam Clues:
    “Fault-tolerant”
    “Can be interrupted”
    “Batch jobs / flexible timing”
👉 Answer = Spot Instances

🚀 3. Short Tasks → Lambda
✅ Use:
     AWS Lambda
💡 Why?
     Pay per execution
     No idle cost
🧠 Exam Clues:
    “Short-lived tasks”
    “Event-driven”
    “No server management”
👉 Answer = Lambda

⚠️ TRAP: Flexible Compute Across Services
❗ Question Pattern:
    “Flexible usage across services”
    “Workload changes instance types / services”
✅ Correct Answer:
👉 Savings Plans
💡 Why?
     Applies across:
         EC2
         Lambda
         Fargate
         Not tied to specific instance types
❌ Wrong Answer:
Reserved Instances
→ Locked to instance type/region (less flexible)

| Scenario               | Answer             |
| ---------------------- | ------------------ |
| Predictable workload   | RI / Savings Plans |
| Interruptible workload | Spot Instances     |
| Short-lived compute    | Lambda             |
| Flexible usage         | Savings Plans      |

# Storage Cost Optimization
💾 1. Lifecycle Policies → Move S3 → Glacier
✅ Use:
     Amazon S3 Lifecycle Policies
     Transition to:
        Amazon S3 Glacier
💡 Why?
     Automatically moves data to cheaper storage over time
     No manual intervention
🧠 Exam Clues:
    “Automatically move older data”
    “Reduce storage cost over time”
👉 Answer = Lifecycle policies

📦 2. Infrequent Access → S3 IA / One Zone IA
✅ Use:
     S3 Standard-IA
     S3 One Zone-IA
💡 Differences:
     Storage Class	     Use Case
     Standard-IA	     Durable, multi-AZ
     One Zone-IA	     Cheaper, single AZ
💡 Why?
     Lower cost than standard S3
     Still instant retrieval
🧠 Exam Clues:
    “Accessed occasionally”
    “Need quick access”
👉 Answer = S3 IA

🧊 3. Archive → Glacier / Deep Archive
✅ Use:
     Amazon S3 Glacier
     Amazon S3 Glacier Deep Archive
💡 Differences:
     Storage	     Retrieval Time
     Glacier	     Minutes–hours
     Deep Archive	Hours
💡 Why?
     Extremely low cost
     Designed for long-term storage
🧠 Exam Clues:
    “Archive”
    “Rarely accessed data”
    “Compliance storage”
👉 Answer = Glacier / Deep Archive

⚠️ TRAP: Rare Access BUT Instant Retrieval
❗ Question Pattern:
    “Rarely accessed”
    “Must retrieve immediately”
✅ Correct Answer:
👉 S3 Standard-IA
💡 Why?
     Provides:
        Lower cost
        Instant access (milliseconds)
❌ Wrong Answer:
 Glacier
→ retrieval delay (minutes to hours)

| Scenario                    | Answer       |
| --------------------------- | ------------ |
| Automatic cost optimization | S3 Lifecycle |
| Infrequent but fast access  | S3 IA        |
| Archive storage             | Glacier      |
| Ultra-cheap archive         | Deep Archive |
| Rare + instant retrieval    | S3 IA        |

# Database Cost Optimization
🗄️ 1. Serverless Database → Aurora Serverless
✅ Use:
     Amazon Aurora Serverless
💡 Why?
     Automatically scales capacity up/down
     Pay only for what you use
🧠 Exam Clues:
    “Intermittent usage”
    “Unpredictable workload”
    “Cost-efficient database”
👉 Answer = Aurora Serverless

⚡ 2. No Administration → DynamoDB
✅ Use:
     Amazon DynamoDB
💡 Why?
     Fully managed (no servers, no patching)
     Automatic scaling
     Pay-per-request option
🧠 Exam Clues:
    “No operational overhead”
    “Fully managed database”
👉 Answer = DynamoDB

📉 3. Right-Sizing → Smaller Instances
✅ Use:
     Adjust DB instance types (RDS/Aurora)
💡 Why?
     Avoid over-provisioning
     Reduce unnecessary cost
🧠 Exam Clues:
    “Underutilized resources”
    “Reduce cost without redesign”
👉 Answer = Right-sizing

⚠️ TRAP: Variable Workload Database
❗ Question Pattern:
    “Workload fluctuates”
    “Unpredictable usage patterns”
✅ Correct Answer:
👉 Aurora Serverless
💡 Why?
     Automatically scales:
     Compute capacity
     Based on demand
❌ Wrong Answers:
     Provisioned RDS → fixed capacity
     Large instances → wasteful

| Scenario                 | Answer               |
| ------------------------ | -------------------- |
| Serverless relational DB | Aurora Serverless    |
| No admin / NoSQL         | DynamoDB             |
| Reduce cost              | Right-size instances |
| Variable DB workload     | Aurora Serverless    |

# Network Cost Optimization
👇

🌐 1. Reduce Data Transfer → CloudFront
✅ Use:
     Amazon CloudFront
💡 Why?
     Caches content at edge locations
     Reduces:
         Data transfer from origin (S3/EC2)
         Latency
🧠 Exam Clues:
    “Reduce bandwidth cost”
    “Global users accessing content”
👉 Answer = CloudFront

🚫💸 2. Avoid NAT Gateway Cost → VPC Endpoints
✅ Use:
     VPC Endpoints:
         Gateway Endpoint
         Interface Endpoint
💡 Why?
     NAT Gateway charges:
         Hourly + data processing fees
     VPC Endpoints:
         Private access to AWS services
         Avoid internet routing → cheaper
🧠 Exam Clues:
    “Private subnet accessing AWS services”
    “Reduce NAT cost”
👉 Answer = VPC Endpoints

🔗 3. Internal Traffic → VPC Peering / PrivateLink
✅ Use:
     VPC Peering
     PrivateLink
💡 Why?
     Keep traffic inside AWS network
     Avoid internet + reduce cost
💡 Differences:
     Service	        Use Case
     VPC Peering	Direct VPC-to-VPC
     PrivateLink	Service-based access
🧠 Exam Clues:
    “Private communication between VPCs”
👉 Answer = Peering / PrivateLink

⚠️ TRAP: Cheap S3 Access from Private Subnet
❗ Question Pattern:
    “Access S3 from private subnet”
    “Minimize cost”
✅ Correct Answer:
👉 Gateway VPC Endpoint
💡 Why?
     Gateway Endpoint for S3:
         FREE
         No NAT required
         Private access
❌ Wrong Answers:
     NAT Gateway → costly
     Internet Gateway → not for private subnet

| Scenario                       | Answer                |
| ------------------------------ | --------------------- |
| Reduce data transfer cost      | CloudFront            |
| Avoid NAT cost                 | VPC Endpoint          |
| Private VPC communication      | Peering / PrivateLink |
| S3 from private subnet (cheap) | Gateway Endpoint      |

