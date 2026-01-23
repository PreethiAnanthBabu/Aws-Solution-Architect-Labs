# EFS(Elastic File System):
     EFS is a fully managed(Serverless), scalable file system in AWS that you can share across multiple servers at the same time.
# What EFS is:
    -A network file system (NFS) in the cloud
    -Designed to be mounted on multiple EC2 instances simultaneously
    -Works like a shared folder that many servers can read from and write to.
# Key features
    -Elastic – automatically grows and shrinks as you add/remove files
    -Fully managed – no capacity planning or maintenance
    -Highly available – data is stored across multiple Availability Zones
    -POSIX-compliant – behaves like a traditional Linux file system
# Common use cases
    -Shared application files (e.g., web servers behind a load balancer)
    -Container storage (EKS, ECS)
    -Content management systems (WordPress, Drupal)
    -Big data & analytics workloads
    -Home directories for users
# EFS vs EBS
   -EBS → attached to one EC2 at a time
   -EFS → shared across many EC2s
# EFS vs S3
   -S3 → object storage (not mountable like a filesystem)
   -EFS → file storage (mount with NFS, supports file locking)
