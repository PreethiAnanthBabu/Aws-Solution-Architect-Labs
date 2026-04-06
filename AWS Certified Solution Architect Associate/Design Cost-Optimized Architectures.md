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

