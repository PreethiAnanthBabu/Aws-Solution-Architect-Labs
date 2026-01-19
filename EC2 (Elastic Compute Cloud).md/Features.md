# Amazon EC2::
     Amazon EC2 provides scalable, on-demand compute capacity in the form of virtual machines, allowing users to run applications with configurable CPU, memory, networking, 
     and storage.

# Key EC2 Concepts:
    -Instance: A virtual server
    -AMI (Amazon Machine Image): Template used to launch an instance (OS + software)
    -Instance Type: Defines CPU, memory, storage, and networking capacity
    -EBS (Elastic Block Store): Persistent storage for instances
    -Security Groups: Virtual firewalls for instances
    -Key Pair: Used for SSH access     

# EC2 Instance Types (Families):
    1. General Purpose (Balanced) -Best for most applications.
       Family	Use Case
          -t3 / t4g  	Burstable workloads (low-cost, dev/test)
          -m5 / m6i  	Web servers, app servers
          -a1	        ARM-based, cost-effective
    2. Compute Optimized (High CPU) -Best for compute-heavy workloads.
       Family	Use Case  
         -c5 / c6i	  High-performance web servers
         -c7g	        ARM-based compute workloads
    3. Memory Optimized (High RAM) -Best for memory-intensive applications.
       Family	Use Case
         -r5 / r6i	  Databases, in-memory caches
         -x2idn	      SAP HANA, large memory apps
         -z1d	        High memory + high CPU
    4. Storage Optimized (High IOPS / Throughput) -Best for fast local storage.
       Family	Use Case
         -i3 / i4i	  NoSQL databases
         -d3	        Data warehousing
         -h1	        Big data workloads
    5.Accelerated Computing (GPU / FPGA) -Best for ML, graphics, and HPC.
      Family	Use Case
        -p4 / p5	    Machine learning training
        -g5	          Graphics, game streaming
        -f1	          FPGA workloads
        -inf2	        AI inference
# Instance Size Naming:
    Example: m5.large
       m → instance family
       5 → generation
       large → size (CPU/RAM capacity)
       Sizes scale like: nano → micro → small → medium → large → xlarge → 2xlarge → 4xlarge
# Pricing Models: 
    -On-Demand – Pay per second
    -Reserved Instances – 1 or 3-year commitment (cheaper)
    -Savings Plans – Flexible commitment
    -Spot Instances – Up to 90% cheaper (can be interrupted)

# Elastic IP:
     Normal public IPs change when an instance is stopped and started.Elastic IP remains the same even after stop/start
     Useful for production servers and DNS mapping  
# Key Features
    -Static IPv4 address
    -Region-specific
    -Can be moved between instances
    -One Elastic IP is free only when attached to a running instance

# AMI(Amazon Machine Image):
     An AMI (Amazon Machine Image) is a preconfigured template used to launch EC2 instances in AWS.
# What an AMI Includes
    -Operating System (Linux / Windows)
    -Application software
    -Configuration settings
    -Root volume snapshot (EBS)
# Why AMI is Important
    -Launch multiple identical EC2 instances
    -Faster provisioning
    -Consistent environments
    -Easy backup and recovery
# Types of AMIs
    -AWS-provided AMIs (Amazon Linux, Windows)
    -Marketplace AMIs (paid/free third-party software)
    -Custom AMIs (created by users)
# When to Use What
    -Use AMI when you need full OS control
    -Use Docker when you want fast, portable, scalable deployments
    

