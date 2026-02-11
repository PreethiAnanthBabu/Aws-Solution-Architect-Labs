# VPC:
     A VPC (Virtual Private Cloud) in AWS is your own private network inside the AWS cloud.A VPC is regional.
     VPC provides:
        -Network isolation
        -Security control
        -Custom IP addressing
        -Hybrid connectivity (VPN / Direct Connect)
        -High availability across multiple AZs   
# CIDR Range (Classless Inter-Domain Routing):
     IPv4 Classes:
     
     | Class | IP Range                    | Default Subnet | Use                              |
     | ----- | --------------------------- | -------------- | -------------------------------- |
     | **A** | 1.0.0.0 – 126.255.255.255   | /8             | Large organizations (many hosts) |
     | **B** | 128.0.0.0 – 191.255.255.255 | /16            | Medium-sized networks            |
     | **C** | 192.0.0.0 – 223.255.255.255 | /24            | Small networks                   |
     | **D** | 224.0.0.0 – 239.255.255.255 | N/A            | Multicast (streaming, video)     |
     | **E** | 240.0.0.0 – 255.255.255.255 | N/A            | Experimental / Research          |

     Private IP Address Ranges:
      
     | Class | Private IP Range              | CIDR |
     | ----- | ----------------------------- | ---- |
     | **A** | 10.0.0.0 – 10.255.255.255     | /8   |
     | **B** | 172.16.0.0 – 172.31.255.255   | /12  |
     | **C** | 192.168.0.0 – 192.168.255.255 | /16  |

     CIDR defines the IP range of a VPC or subnet and determines how many IP addresses are available.Max is 28 and min 16.
     Formula:
         How many IPs in /X
         32 - X = remaining bits
         2^(remaining bits)
     Subnet Range:
         2 subnets → borrow 1 bit
         4 subnets → borrow 2 bits ✅
         So 
         /16  - /17( 2 Subnets)
         /16  - /18( 4 Subnets)
     When does the octet change?
         /8 – /15 	2nd octet
         /16 – /23	3rd octet ✅
         /24 – /31	4th octet
     Example 1:                                                           Example 2:
         CIDR Range = 10.0.0.0/16 into 4 subnets                              CIDR Range = 10.0.0.0/24 into 2 subnets
         32-16= 16                                                            32-24= 8
         2^16 = 65536 IP's                                                    2^8 = 256 IP's
         Subnet range = 10.0.0.0/18                                           Subnet Range = 10.0.0.0/25
             The third number now moves in blocks                                 The Fourth octet now moves in blocks
             Each block is 64 numbers wide (256 ÷ 4 = 64)                         Each block is 128 numbers wide (256÷2 =128) 
             The original third octet goes from:0 → 255                           The original Fourth octet goes from:0 → 255
             Split that into 4 equal chunks:                                      Split that into 4 equal chunks:
             0   → 63                                                             0   → 127
             64  → 127                                                            128 → 255
             128 → 191                                                            Subnet 1:
             192 → 255                                                              10.0.0.0/25
             Subnet 1:                                                              Range: 10.0.0.0 → 10.0.0.127/25
                  10.0.0.0/18                                                     Subnet 2:
                  Range: 10.0.0.0 → 10.0.63.255                                     10.0.0.128/25                             
             Subnet 2:                                                              Range: 10.0.0.128 → 10.0.0.255
                  10.0.64.0/18
                  Range: 10.0.64.0 → 10.0.127.255
             Subnet 3:
                  10.0.128.0/18
                  Range: 10.0.128.0 → 10.0.191.255
             Subnet 4:
                  10.0.192.0/18
                  Range: 10.0.192.0 → 10.0.255.255

# Subnets:
     A subnet is a smaller network inside a VPC, tied to a single Availability Zone.
     Types:
      🔹 Public Subnet
            -Has route to Internet Gateway
            -Used for Load Balancers, Bastion Hosts
      🔹 Private Subnet
            -No direct internet route
            -Used for App servers, Databases
# Route Tables:
    A route table controls where network traffic goes.Each subnet is associated with one route table.
    Types:
      -Main route table (default)
      -Custom route tables
# Internet Gateway (IGW):
    An Internet Gateway enables communication between VPC and Internet.It is:
      -Attached to VPC
      -Horizontally scalable
      -Managed by AWS
    For a subnet to be public:
      -VPC must have IGW attached
      -Subnet route table must contain: 0.0.0.0/0 → IGW
      -Instance must have public IP
# NAT Gateway:
    Allows private subnet instances to access the internet.WITHOUT allowing inbound internet traffic.
    Used for:
      -OS updates
      -Downloading packages
      -Accessing APIs
# Network ACL (Access Control List):
    Network ACL is a stateless subnet-level firewall that controls inbound and outbound traffic for subnets.
    Key Characteristics:
      -Stateless
      -Evaluates inbound AND outbound rules
      -Rules are numbered
      -Allows and Denies both possible 
    Example:
      | Rule # | Type | Source    | Allow/Deny |
      | ------ | ---- | --------- | ---------- |
      | 100    | HTTP | 0.0.0.0/0 | Allow      |
      | 200    | ALL  | 0.0.0.0/0 | Deny       |
   
    Security Group vs NACL:
      Security Groups are stateful, meaning return traffic is automatically allowed if inbound traffic is permitted. Network       ACLs are stateless, so both inbound and outbound rules must be explicitly defined because the NACL does not track            connection state.
    
      | Security Group | NACL         |
      | -------------- | ------------ |
      | Instance-level | Subnet-level |
      | Stateful       | Stateless    |
      | Allow only     | Allow & Deny |
