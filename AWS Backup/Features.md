# AWS Backup:
      It is a fully managed service from Amazon Web Services that centralizes and automates data protection across AWS services and on-premises environments.
   
# What AWS Backup Does
     -Create automated backup plans for AWS resources
     -Schedule backups (daily, weekly, monthly)
     -Retain backups for set periods
     -Copy backups across regions/accounts
     -Restore resources quickly and consistently
     -Monitor compliance with backup policies

# Key Components
  1. Backup Plan
     Defines:
          -Backup rules
          -Schedule (cron or simple)
          -Lifecycle (cold storage transition + expiration)
          -Copy rules (cross-region/cross-account)

  2. Backup Vault
          -Encrypted storage container for backups
          -You can apply resource-based policies for cross-account access
          -You can enforce a Vault Lock (WORM: Write Once, Read Many), preventing deletions even by admins

  3. Protected Resources
          -Resources that are being backed up according to a plan.

4. Recovery Points
          -Actual backups—can be full or incremental.
     
# AWS Backup vs. Snapshots
     -Snapshots are service-specific (e.g., EBS snapshot → only for EBS).
     -AWS Backup provides centralization, scheduling, policies, and compliance, covering many services.

    
