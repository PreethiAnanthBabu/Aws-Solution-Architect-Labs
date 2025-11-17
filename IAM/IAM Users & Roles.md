# IAM User 
    An IAM User represents a person or an application that needs long-term access to AWS.  

# Key Characteristics:
    -Has a permanent identity in AWS.
    -Can have long-term credentials
       Username/password (for AWS Console login)
       Access key & secret key (for CLI/SDK)
    -Can be assigned to groups to inherit permissions.
    -Typically used for employees, developers, or service accounts (but using roles is better for automation).

# Use Cases:
    -A developer logging into the AWS console.
    -Human users that need persistent access.

 # IAM Roles
      IAM Roles are temporary, assumed identities designed for AWS services, cross-account access, and federated authentication. 
      Roles don’t have long-term credentials and are therefore more secure and scalable

# Key Characteristics:
    -Not a person—an identity that any trusted entity can assume.
    -Provides temporary credentials issued by STS.
    -No password, no access keys stored anywhere.

# Use Case: 
    -EC2 instance needs S3/ECR access
    -Lambda needs permissions to call DynamoDB
    -Pod in EKS needs to read Secrets Manager (IRSA)
    -cross-account access
    -Temporary access without keys
    -Federated authentication from AD/Okta
