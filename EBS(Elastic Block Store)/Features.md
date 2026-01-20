# Elastic Block store:
     Amazon EBS is a managed block storage service that provides persistent, scalable, and high-performance storage for Amazon EC2 instances.EBS is like a virtual hard drive in the cloud that you attach to a server (EC2).
# Key points about Amazon EBS
    1. Persistent storage
         -Data remains even if the EC2 instance is stopped or restarted
         -Unlike instance store, data is not lost when the instance stops
    2. Block storage
         -Works like a traditional disk (you can format it, create files, install databases)
         -Ideal for OS disks, databases, and applications that need low-latency access
    3. Attach/detach
         -You can attach an EBS volume to an EC2 instance
         -Detach it and attach it to another instance if needed
    4. High availability
         -Volumes are automatically replicated within an Availability Zone (AZ)
         -Protects against hardware failure (but not AZ failure)
    5. Scalable
         -You can change volume size, type, and performance without stopping the instance (for most cases)
# Common EBS volume types
    1. gp3 / gp2 – General purpose (most workloads)
    2. io1 / io2 – High-performance, mission-critical databases
    3. st1 – Throughput-optimized (big data, logs)
    4. sc1 – Cold storage (infrequently accessed data)
# Typical use cases
    1. Root volume for EC2
    2. Databases (MySQL, PostgreSQL, Oracle)
    3. Application file systems
    4. Boot volumes
