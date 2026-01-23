AWS Console > EFS > Create File system > EC2 > Create 3 Linux based instances with same security group > Instances > Security group > Edit Inbound rules > allow nfs port from anywhere > EFS > Network > add ec2 security group in EFS > Save > Login to 3 ec2 instances with putty > Install amazon efs utility in 3 instance and create directory
" sudo -i
  yum install -y amazon-efs-utils
  mkdir efs "
> AWS Console > EFS > Attach > Copy the efs mount helper and paste it in 3 instances > Now the efs is successfully mounted in 3 ec2 instances > create sample file in one instance and it will appear in all instances
" sudo mount -t efs -o tls fs-0295a48be63c1b399:/ efs
  cd efs
  echo "content" >File1.txt
  cat File1.txt "
