AWS Console > Create EC2 Linux Instance > Connect with the Linux Instance > Install docker 
   " Sudo -i
    yum install docker -y
    service docker status
    service docker start "
> pull httpd image from docker hub
  " docker pull httpd 
    docker images "
> Aws Console > ECR > Create Repository > AWS COnsole > IAM > Policies > Create Policy > Click JSON
  " {
    "Version":"2012-10-17",		 	 	 
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "ecr:CompleteLayerUpload",
                "ecr:GetAuthorizationToken",
                "ecr:UploadLayerPart",
                "ecr:InitiateLayerUpload",
                "ecr:BatchCheckLayerAvailability",
                "ecr:PutImage"
            ],
             "Resource": "*"
        }
    ]
}
> Create policy > Roles > Create role > Select EC2 > Select the created role > Create role > EC2 > Select the Instance and Modify IAM Role 
> ECR > View push commands > Copy the authentication code and paste it in EC2 Linux instance 
  " aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 995876471567.dkr.ecr.us-east-1.amazonaws.com
> Login succeeded > copy the tag and push command from the ecr and paste it in EC2 Linux instance 
  " docker tag demorepository:latest 995876471567.dkr.ecr.us-east-1.amazonaws.com/demorepository:latest
    docker push 995876471567.dkr.ecr.us-east-1.amazonaws.com/demorepository:latest "
> Now we can see our image in ecr repository > AWS Console > ECS > create cluster > Select Fargate and managed instance 
> create clusters > AWS Console > IAM > Roles > Create new role > select aws services:ecs-tasks with these policy permissions 
  " AmazonECSTaskExecutionRolePolicy
    CloudWatchLogsFullAccess "
> Task definition > create new task definition > select the taskrole which we have created and give container name and image URI
and port > create task definition > clusters > service > create new service > Tasks > click running tasks > select public IP
> Now we can see the output 

