# Command line options 
Command	                     Meaning
git -v	                   short option
git --version              long option
terraform -version	       Terraform's defined option

--	commonly means "end of options" when used by itself
- vs -- is a command-line interface convention, and the individual program decides which options it supports.

# CI/CD pipeline
AWS Terraform 3-tier project having two separate parts:
Terraform builds the infrastructure. CI/CD deploys the application into that infrastructure.
Terraform part creates things like:
   VPC
   Subnets
   Internet Gateway
   NAT Gateway
   Security Groups
   ALB
   Target Group
   Launch Template
   Auto Scaling Group
   EC2
   RDS
   IAM Roles
CI/CD pipeline handles application files, such as:
   index.html
   appspec.yml
   buildspec.yml
   scripts/restart_nginx.sh
# Flow

You change code in VS Code
        ↓
Push to GitHub
        ↓
CodePipeline detects the change
        ↓
CodeBuild prepares/builds the application
        ↓
CodeDeploy deploys it to EC2
        ↓
Nginx serves the new index.html
        ↓
Users access it through the ALB

# CodePipeline
CodePipeline is the overall workflow controller.It connects all the stages together:
   Source → Build → Deploy

# CodeBuild
CodeBuild takes your source files and runs instructions from buildspec.yml.
For a simple HTML project, there may not be much actual compiling. It can simply package or prepare the files for deployment.
A buildspec.yml might tell CodeBuild:
   Take:
   index.html
   appspec.yml
   scripts/
   and pass them to the next stage
In a bigger application, CodeBuild could also:
   install dependencies
   run tests
   compile code
   build Docker images
   package artifacts

# Codedeploy
CodeDeploy is responsible for putting your application onto the EC2 instances.
It reads: appspec.yml
CodeDeploy = deploy files and run deployment scripts on EC2.

# Git commands
git init - This initializes Git inside your current project folder. It creates a hidden .git directory so Git can start tracking versions of your files.

git add . - prepare all current project files for commit

git commit -m "Initial AWS Terraform 3 tier project" - It creates a Git commit from the files you previously staged with git                                                        add .
                                                     -m(add the commit message directly)

git branch -M main - renames current Git branch to main
                   -M(force the rename if needed)

git remote add origin YOUR_GITHUB_REPOSITORY - This command connects your local project to that GitHub repository and gives                                                 the remote the name origin.
                                                     
git remote -v - Displays the GitHub URL for fetch and push.

git push -u origin main - This command pushes local main branch to the GitHub remote named origin
                        -u(Uploads local files to github)











