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
       Host DNS zones and records.Records live inside a Hosted Zone, and Name Servers publish that Hosted Zone to the               internet.
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

# Routing Policies:
     A routing policy in Amazon Route 53 is a set of rules that controls how DNS queries are answered—specifically, which endpoint (IP address, load balancer, or resource) a user is directed to when they request a domain name.

# Types:
     1. Simple Routing 
          -Route 53 stores one DNS record for a domain.
          -Whenever a DNS query comes, it always returns the same single IP/endpoint.
          -There is no decision-making logic.
          -It does not evaluate health or conditions.
          -In simple words:
             “Every user always gets the same destination.”
     2. Weighted Routing 
          -Multiple DNS records exist for the same domain name.
          -Each record is assigned a numeric weight.
          -When a DNS query arrives, Route 53:
              Calculates the probability based on weights
              Randomly returns one record according to that probability
          -Example logic:
               If weights are 80 and 20
               → About 80% users go to resource A, 20% to B.
     3. Latency-Based Routing 
          -Route 53 maintains latency measurement data between AWS regions and user networks.
          -When a user makes a DNS query:
               Route 53 identifies the user’s location (network)
               Checks which AWS region has lowest measured latency
               Returns the DNS record mapped to that fastest region
               It does not use distance — it uses actual network latency data.
          -Conceptually:
               “User is sent to the resource that responds the fastest over the network.” 
     4. Failover Routing
          -Two DNS records exist:
                Primary
                Secondary
          -A health check continuously monitors the Primary.
          -When a DNS query comes:
                If Primary is healthy → return Primary IP
                If Primary is unhealthy → return Secondary IP
          -Failover happens at DNS resolution time, not during an active session.
          -Conceptually:
                “Use the main site when it’s healthy, otherwise switch to backup.”
     5. Geolocation Routing 
          -Route 53 determines user’s geographic location from IP address.
          -DNS records are mapped to:
                Countries
                Continents
                Or a Default location
          -When a query arrives:
                User’s country is identified
                Matching geographic rule is selected
                Corresponding DNS record is returned
                If no match → Default record is returned
          -Conceptually:
                “Users are routed based on their country/continent, not performance.”
     6. Geoproximity Routing — How it Works
         -Route 53 calculates the physical distance between user and resources.
         -It then optionally applies a bias value:
                Positive bias → attracts more traffic
                Negative bias → repels traffic
         -DNS response is chosen based on:
                Distance
                Plus/minus configured bias
                Unlike geolocation, this is based on distance, not political boundaries.
         -Conceptually:
                “Users go to the closest resource, unless bias shifts them elsewhere.”






            
