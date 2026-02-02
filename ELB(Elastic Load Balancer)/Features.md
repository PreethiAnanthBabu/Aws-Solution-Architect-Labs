# ELB:
     A load balancer distributes incoming traffic across multiple servers to improve availability, performance, and fault tolerance.
     Users → Load Balancer → Multiple Servers → App works ✅
# Load Balancer Does:
    -Distributes traffic evenly
    -Checks server health
    -Sends traffic only to healthy servers
    -Improves:
        Availability
        Scalability
        Performance
# Load Balancing algorithm:
     A load-balancing algorithm decides which server should handle the next request.
     1.Round Robin (Most Basic)
       How it works: Requests are sent one by one to each server in order
       Example:
           Request 1 → Server A
           Request 2 → Server B 
           Request 3 → Server 
           Request 4 → Server A
       ✅ Simple
       ❌ Doesn’t consider server load
       
     2.Weighted Round Robin
     How it works: Servers with more power get more traffic
     Example:
         Server A (weight 3)
         Server B (weight 1)
         A → A → A → B → A → A → A → B
     ✅ Better than round robin
     ❌ Still not real-time load aware  
     
    3.Least Connections
      How it works: Sends traffic to the server with the fewest active connections
      ✅ Great for:
             Long-running connections
             Uneven traffic
      ❌ Slightly more overhead

    4.Least Response Time
      How it works: Chooses the server that responds fastest
      ✅ Good for performance
      ❌ More complex

    5.Hashing Method
      How it works: The hashing method is a load-balancing technique where the same client is always sent to the same server.
      Example:
          Client sends a request
          Load balancer takes a value (e.g. client IP)
          Applies a hash function
          Hash result maps to a server
          Request is sent to that server
          Client IP → Hash Function → Server B
          Same IP → same hash → same server
     6.Random
       How it works: Randomly picks a server
       ✅ Very simple
       ❌ Unpredictable load distribution
# Types of Load Balancers:
     Load balancers are mainly classified by where they work and what they understand.
     🔹 Application Load Balancer (ALB)
         Works at Layer 7(Application Layer)
         Understands HTTP/HTTPS
         Can route like:
             /login → server A
             /api → server B
         Supports:
             Microservices
             Kubernetes
             AWS WAF
         👉 Best choice for modern apps
     🔹 Network Load Balancer (NLB)
         Works at Layer 4(Transport Layer)
         Very fast
         Doesn’t look inside HTTP
         Handles:
             Millions of requests
             TCP / UDP traffic
             Supports static IP
         👉 Best for performance and low latency
     🔹 Classic Load Balancer (CLB)
         Old AWS load balancer
         Can work at Layer 4 or 7
         Very limited features
         No modern routing
         👉 AWS does NOT recommend it for new apps
     
     
