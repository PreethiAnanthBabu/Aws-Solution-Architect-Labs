# Global Infrastructure:
     AWS Global Infrastructure is the worldwide network of data centers and networking components that allows AWS to deliver services with high availability, low latency, scalability, and fault tolerance.
    1.Region -A Region is a geographical area where AWS has multiple data centers.
      Key points
       -Each Region is independent
       -Data does not move between Regions unless you configure it
       -You choose a Region when launching resources
      Example Regions
       -us-east-1 – North Virginia
       -eu-west-1 – Ireland
       -ap-south-1 – Mumbai
    2.Availabilty Zone -Availability Zones are isolated data centers within a Region that provide fault tolerance and high availability.
      Key points
       -Each Region has 2 or more AZs
       -AZs are isolated from each other
       -Connected with high-speed, low-latency links
       -Designed for high availability and fault tolerance
      Example
       -Region: eu-west-1 (Ireland)
       -AZs: eu-west-1a, eu-west-1b, eu-west-1c
    3.Edge Locations -An Edge Location is a site where AWS delivers content closer to end users.
      Key points
       -Used mainly for content delivery
       -Reduce latency
       -Do not host full applications
       -Located in many cities worldwide
      Example
       -User in India accesses content cached at a nearby Edge Location instead of going to the main AWS Region
    4.AWS Outposts -AWS infrastructure installed on-premises, fully managed by AWS.
      Key points
       -Hybrid cloud
       -Low-latency access to on-prem data
       -Regulatory requirements
    5.Local Zones -A Local Zone is an AWS extension of a Region placed close to a large city or metro area to provide ultra-low latency.
      Key points
      -Physically closer to end users
      -Connected to a parent Region
      -Not designed for multi-AZ fault tolerance
      -Limited AWS services compared to AZs
       
