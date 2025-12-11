# Docker:
     Docker is a software platform that allows you to build, test, and deploy applications quickly. Docker packages software  into standardized units called containers that have everything the software needs to run including libraries, system tools, code, and runtime. Using Docker, you can quickly deploy and scale applications into any environment and know your code will run.
It solves problems like:
     -“It works on my machine but not on the server”
     -Dependency conflicts
     -Complex deployments

# Docker Image:
     A Docker image is a read-only template used to create containers.Images are built using a file called a Dockerfile.
     It contains:
         -Application code
         -Runtime (e.g., Java, Node.js, Python)
         -System libraries
         -Dependencies
         -Environment settings

# Containers:
     A container is a running instance of a Docker image.
     It is:
        -Lightweight
        -Isolated from other containers
        -Shares the host OS kernel
        -Starts in seconds
     You can:
       -Start
       -Stop
       -Restart
       -Delete containers without affecting the image

# Docker Hub:
     Docker Hub is a cloud-based registry (storage) for Docker images.It is like GitHub for Docker images.
     You can:
       -Pull public images (e.g., nginx, mysql, redis, ubuntu)
       -Push your own custom images
       -Share images with teams
       
# Difference Between Docker Image and Virtual Machine (VM)
     Feature	              Docker Image / Container	                  Virtual Machine (VM)
     Architecture	          Shares host OS kernel	                      Has its own full OS
     Size	                  Small (MBs)	                                Large (GBs)
     Boot Time	            Seconds	                                    Minutes
     Performance	          Near native speed	                          Slower due to full OS
     Resource Usage	        Very low	                                  High
     Isolation	            Process-level isolation	                    Full hardware-level isolation
     Portability	          Extremely portable	                        Less portable

# Real-World Example
     If you deploy a Python app:
     With VM:
       -Install OS → Install Python → Install libraries → Deploy app
       -Heavy and slow
     With Docker:
       -Just run:
           " docker run my-python-app "
       -Everything is already inside the image
       -Fast, consistent, portable

  
