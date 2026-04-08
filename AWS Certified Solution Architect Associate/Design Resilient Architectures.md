# High Availability (HA) & Fault Tolerance (FT)
♻️ 1. Multi-AZ → High Availability (HA)
✅ Use:
     Amazon RDS
     Application Load Balancer
     Amazon EC2 Auto Scaling
💡 What is Multi-AZ?
     Resources deployed across multiple Availability Zones
     Same region, different data centers
💡 Why?
     Automatic failover
     Protects against AZ failure
🧠 Exam Clues:
    “High availability within a region”
    “Automatic failover”
👉 Answer = Multi-AZ

🌍 2. Multi-Region → Disaster Recovery (DR)
✅ Use:
     Deploy across:
        Multiple AWS regions (e.g., Ireland + Frankfurt)
💡 Why?
     Protects against:
        Region-wide outages
        Large-scale disasters
💡 DR Strategies (know keywords):
     Backup & Restore
     Pilot Light
     Warm Standby
     Active-Active
🧠 Exam Clues:
    “Disaster recovery”
    “Region failure”
👉 Answer = Multi-Region

🧠 3. Stateless Applications
✅ Store state externally in:
     Amazon DynamoDB
     Amazon ElastiCache
     Amazon S3
💡 Why?
     Instances can:
        Scale in/out freely
        Be replaced without data loss
🧠 Exam Clues:
    "Scalable web app”
    “Session persistence problem”
👉 Answer = Stateless + external storage

🌍 4.Global Downtime Minimization
❗ Question Pattern:
    “Minimize downtime globally”
    “Users worldwide need high availability”
✅ Correct Answer:
Use:
     Amazon Route 53
     Health Checks
     Failover Routing Policy
💡 Why?
     Route 53:
         Detects endpoint health
         Automatically reroutes traffic
🧠 Routing Types to Know:
     Failover → Primary → Secondary
     Latency-based → nearest region
     Weighted → traffic splitting
❌ Common Wrong Answers:
     Only Multi-AZ (not global)
     Only Auto Scaling (not cross-region)

| Scenario                        | Answer                   |
| ------------------------------- | ------------------------ |
| High availability (same region) | Multi-AZ                 |
| Disaster recovery               | Multi-Region             |
| Scalable app design             | Stateless + DynamoDB/S3  |
| Global failover                 | Route 53 + health checks |

# Disaster Recovery (DR) strategies
🔄 1. Key Concepts (Must Know First)
💡 Abbreviations:
     RTO (Recovery Time Objective)
        → How fast you recover (downtime)
     RPO (Recovery Point Objective)
        → How much data you can lose
🧠 Simple Memory:
     RTO = Time ⏱️
     RPO = Data 📦

💾 2. Backup & Restore → Cheapest, Slowest
💡 How it works:
     Take backups (e.g., S3, snapshots)
     Restore when disaster happens
✅ Pros:
     Very cheap
❌ Cons:
     High RTO (slow recovery)
     High RPO (possible data loss)
🧠 Exam Clue:
    “Low cost solution”
👉 Answer = Backup & Restore

🔥 3. Pilot Light → Minimal Always Running
💡 How it works:
     Core components always running (e.g., DB)
     App servers launched during failure
✅ Pros:
     Faster than backup
     Moderate cost
❌ Cons:
     Still some startup delay
🧠 Exam Clue:
    “Critical core system always running”

🌤️ 4. Warm Standby → Scaled-Down Environment
💡 How it works:
     Full system running in another region
     Smaller capacity
✅ Pros:
     Faster recovery than Pilot Light
❌ Cons:
     Higher cost
🧠 Exam Clue:
    “Reduced capacity environment already running”
👉 Answer = Warm Standby

🌍 5. Multi-Site Active/Active → Fastest, Most Expensive
💡 How it works:
     Full system running in multiple regions
     Traffic distributed across regions
✅ Pros:
     Near-zero downtime
     Near-zero data loss
❌ Cons:
     Most expensive
     Complex
🧠 Exam Clue:
    “Highly available globally”
    “No downtime”
👉 Answer = Active/Active

⚠️ TRAP: RTO/RPO Near Zero
❗ Question Pattern:
    “RTO and RPO must be near zero”
    “Minimal downtime and no data loss”
✅ Correct Answer:
👉 Multi-site Active/Active
💡 Why?
     System is already running everywhere
     No need to “recover”—just reroute traffic
❌ Wrong Answers:
     Warm Standby → still some delay
     Pilot Light → requires scaling up
     Backup → too slow

| Strategy         | Cost     | RTO       | RPO       |
| ---------------- | -------- | --------- | --------- |
| Backup & Restore | 💲       | High      | High      |
| Pilot Light      | 💲💲     | Medium    | Medium    |
| Warm Standby     | 💲💲💲   | Low       | Low       |
| Active/Active    | 💲💲💲💲 | Near Zero | Near Zero |

