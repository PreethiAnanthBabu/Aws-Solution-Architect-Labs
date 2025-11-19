AWS Console > Create 2 EC2 instance > Add NFS in inbound rules in EC2 security group > Create EFS > Network > Add EC2 SG in EFS > Login to EC2 instances using Putty > Install amazon efs utility 
     " sudo -i 
      yum install -y amazon-efs-utility "
> Create directory " mkdir efs " > AWS Console > efs > Attach > Copy the EFS mount helper > Paste in the linux instances > Go to the created directory in one of the ec2 instances " cd efs " > Create new File and content " echo "Content1" >File1 "  > Go to another ec2 instance, now we can see the same file and contents in this instance also  > AWS Backup 
> Vaults > Create new Vault > Dashboard > On-demand backup > Select Resource type > Choose Vault > Select IAM Role >
> Create On-demand backup Vault > Select the Created vault > We can see EFS there
> Actions > Restore > Now another EFS is created with same name but with new endpoint


      
