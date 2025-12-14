AWS Console > Create EC2 Linux instance > allow Http port in inbound rule > Connect with the EC2 instance > Install Docker 
  " Sudo -i
    yum install docker -y
    service docker status
    service docker start "
> Docker hub > Ubuntu > Copy ubuntu image > EC2 Linux > pull and run ubuntu image
  " docker pull ubuntu
    docker run -it ubuntu
    cat /etc/*release*
    exit "
           ( -it                 -interactive mode
              cat /etc/*release* - To see which OS we are in)
> create directory > Go inside the directory > create Dockerfile inside the directory
  " mkdir module1
    cd module1
    vim Dockerfile
    FROM ubuntu
    RUN apt-get update
    CMD["echo","This is my dockerfile"]
           (FROM                                     -  Every Dockerfile must start with FROM (except ARG)
                   Without this, Docker has no OS environment to run commands
            RUN apt-get update                       -  Runs during image build time
                                                        Updates the Ubuntu package index
                                                        Creates a new image layer
            CMD["echo","This is my first dockerfile"] - Defines the default command for the container
                                                        Executes when the container starts )
> Build the Dockerfile
  " docker build tag --demofile1:v1 ."
            ( --demofile1:v1 . - space. is given to search for the Dockerfile in the current directory
> Login to your dockerhub " docker login" > Give username and password > Tag to the dockerhub account
  "docker tag demofile1:V1 preethiananthbabu/demofile1:v1 "
> Push this file into your dockerhub
  "docker push preethiananthbabu/demofile1:v1 "
> Now we can see our dockerfile in Dockerhub account
