# DNS:
     DNS (Domain Name System) is the “phonebook of the internet.”
It translates human-friendly domain names (like google.com) into IP addresses (like 142.250.190.14) that computers use to locate and communicate with each other.

# Key functions of DNS
    -Domain → IP translation
    -Load distribution (via round-robin, etc.)
    -Caching to speed up lookups
    -Hierarchy of DNS servers: Root → TLD (e.g., .com) → Authoritative servers

# Route 53:
     A highly available, scalable, AWS-managed DNS service that adds health checks, traffic routing, domain registration, and deep AWS integration—going beyond basic DNS.

# Key functions of Route 53
    -DNS Hosting  
       Host DNS zones and records (A, AAAA, CNAME, MX, etc.).
    -DNS Records Types
       1. A Record (Address Record)
            Maps a domain to an IPv4 address.
            Example: example.com → 192.0.2.1
       2. AAAA Record
            Maps a domain to an IPv6 address.
            Example: example.com → 2001:db8::1
       3. CNAME Record (Canonical Name)
            Creates an alias from one domain to another domain.
            Example: app.example.com → backend.example.com
            Often used for:
                Subdomain aliasing
                Cloud services (CloudFront, S3, etc.)
       4. MX Record (Mail Exchange)
            Defines where emails should be delivered.
            Example: example.com → mail server like smtp.google.com  
       5. TXT Record
             Stores text information, often used for:
                SPF (email sender policy)
                DKIM
                Domain ownership verification
                Security configs
             Example: "v=spf1 include:_spf.google.com ~all"
       6. NS Record (Name Server Record)
             Defines which DNS servers are authoritative for the domain.
             Example: ns-123.awsdns-45.com
       7. SOA Record (Start of Authority)
             Contains administrative information about the domain:
                Primary name server
                Contact email
                Serial number
                Refresh/Retry timers
                Every domain has exactly one SOA.
       8. PTR Record (Pointer / Reverse DNS)
             Maps an IP address → domain name (reverse of A record).
             Used for:
                Email server validation
                Logging
       9. SRV Record — “Service Record”
             ➡️ Specifies servers for certain services
             💬 “This service runs on this host and port.”
       10. ALIAS / ANAME Record (Route 53 specific)
             Like CNAME but can be used at the root domain (example.com) — CNAME cannot.
             AWS ALIAS supports:
                CloudFront
                ELB
                S3 website
                API Gateway
    -Traffic Routing Policies
       Simple
       Weighted (e.g., 70% → server A, 30% → server B)
       Latency-based routing
       Failover routing
       Geolocation routing
       Multi-value answer routing
    -Health Checks + Failover
       Route 53 can monitor endpoints; if a server goes down, it automatically reroutes traffic.
    -High Availability
       Because it's spread globally through AWS DNS infrastructure.








            
