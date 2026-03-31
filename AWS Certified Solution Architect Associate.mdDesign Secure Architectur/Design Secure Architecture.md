# IAM & Access Control
🔐 1. Cross-Account Access → IAM Role + STS (NOT credentials)
✅ Correct Approach:
Use:
    AWS Identity and Access Management Role
    AWS Security Token Service
💡 Why?
    Roles provide temporary credentials
    No need to share access keys (which is insecure)
    Supports least privilege
🧠 Exam Thinking:
If the question says:
   “Account A needs access to Account B”
   "Secure access between accounts”
👉 Answer = AssumeRole via STS
❌ Wrong:
   Sharing IAM user credentials
   Creating duplicate users across accounts

🏢 2. Large Organization → AWS Organizations + SCPs
✅ Correct Approach:
Use:
    AWS Organizations
    Service Control Policies (SCPs)
💡 Why?
    Centralized account management
    Enforce rules across all accounts
⚠️ Key Exam Concept:
   👉 SCPs do NOT grant permissions — they only restrict
🧠 Strategy:
    Use Deny-first mindset
    SCP = “maximum allowed permissions boundary”
📌 Example:
    Block all accounts from:
       Deleting logs
       Using certain regions

🔑 3. Federated Users → SAML / OIDC
✅ Correct Approach:
Use identity federation with:
    SAML(Security Assertion Markup Language)
    OIDC(OpenID Connect)
Integrations:
    AZURE AD
    OKTA
💡 Why?
    No need to create IAM users
    Users log in with corporate credentials  
🧠 Exam Clue Words:
   “Existing corporate directory”
   “Single sign-on (SSO)”
   “Centralized identity”
👉 Answer = Federation   

🪣 4. Fine-Grained S3 Access
✅ Correct Combination:
   IAM Policies
   Bucket Policies
   (Optional) ACLs (rarely used)
Using:
   Amazon S3
💡 Why multiple layers?
   IAM → user/role permissions
   Bucket policy → resource-level control
   ACL → legacy (avoid unless needed)
🧠 Exam Tip:
👉 Prefer:
    IAM + Bucket Policy
👉 Avoid:
   ACLs unless explicitly required

| Scenario                | Correct Answer          |
| ----------------------- | ----------------------- |
| Cross-account access    | IAM Role + STS          |
| Large multi-account org | AWS Organizations + SCP |
| Corporate login         | SAML / OIDC federation  |
| Temporary access        | IAM Role                |
| S3 fine-grained access  | IAM + Bucket Policy     |
