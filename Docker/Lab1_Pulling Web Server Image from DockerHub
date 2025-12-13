AWS Console > Create EC2 Linux instance > allow Http port in inbound rule > Connect with the EC2 instance > Install Docker 
  " Sudo -i
    yum install docker -y
    service docker status
    service docker start "
> pull httpd image from docker hub
  " docker pull httpd 
    docker images "
> Docker hub > copy from exposing external port > Linux Instance > start an Apache HTTP web server inside a Docker container 
  " docker run -dit --name httpd1 -p 80:80 httpd 
        (  docker run            - Creates and starts a new container.
          -d (detached mode)     - Runs the container in the background.
          -i (interactive)       - Tells Docker to keep the container’s STDIN (standard input) open, even if you’re not actively typing anything.
          -t (TTY)               - Allocates a terminal (often paired with -i).
          --name httpd1          - Gives the container a friendly name (httpd1) instead of a random ID.
          -p 80:80               - Maps: Port 80 on your host machine to port 80 inside the container (Apache’s default port)
           httpd                 - The Docker image being used (official Apache HTTP Server image)  )
> Browser > Hit the public IP > We can see the output

