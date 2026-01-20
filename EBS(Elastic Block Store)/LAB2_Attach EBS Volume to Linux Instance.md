AWS Console > EC2 > Launch Instance > Give Name , keypair(.ppk file), select AMI(Amazon Linux) and network settings (add ssh port from anywhere)
> Launch Instance > > EBS > Volumes > Create volume in same availablity zone as the instance
> select the created volume > action > attach volume > select the Linux instance > EC2
> select the created instance > copy the public IP > Putty > give the public ip as host name > SSH > AUTH > credentials
> browse the downloaded ppk file > open > now we are connected to the linux instance 
> Login as "ec2-user" >
      " lsblk "  (To see all the storage attached to the isntance)
      " sudo mkdir /data "  (to create directory to mount our volume)
      " sudo mkfs -t -f xfs /dev/nvme1n1p2 " (to create a file system for the volume)
      " sudo mount /dev/nvme1n1p2 /data " (to mount the volume)
      " cd /data " (to go inside our volume)
      " sudo chmod 777 /data " (to give appropriate permission to create file inside the mounted volume)
      " echo "Content" >filename.txt " (to create file in the mounted volume and write content in the file)
      " cat filename.txt " (To view the content of the file)
