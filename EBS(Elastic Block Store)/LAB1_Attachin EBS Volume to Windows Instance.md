AWS Console > EC2 > Launch Instance > Give Name , keypair(.pem file), select AMI(Windows) and network settings (add rdp port from anywhere)
> Launch Instance >  select the created instance > Actions > Security > Get windows password > Upload the private key file that we have created
> Decrypt password > Copy the password > connect > rdp client
> download the remote desktop file  > open the rdp file > give password and username as administrator
> Now we're connected to the windows instance > AWS Console > EBS > Volumes > Create volume in same availablity zone as the instance
> select the created volume > action > attach volume > select the window instance 
> In the instance > Computer Management > disk management > new simple volume > give the drive name > next > finish
> Now we can see the attached volume in rdp 
