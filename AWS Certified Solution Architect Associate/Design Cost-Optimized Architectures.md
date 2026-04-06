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


👉 Answer = Spot Instances
