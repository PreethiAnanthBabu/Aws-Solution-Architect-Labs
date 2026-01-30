AWS Console > EC2 > Launch Instance > Give Name , keypair(.pem file), select AMI(Windows) and network settings (add rdp and http port from anywhere) > Launch Instance > select the created instance 
> Actions > Security > Get windows password > Upload the private key file that we have created > Decrypt password > Copy the password > connect > rdp client
> download the remote desktop file  > open the rdp file > give password and username as administrator > Now we're connected to the windows instance > In the instance 
> server manager > add roles and feature > select web server IIS > add feature > next > Install > once installed give the public ip in browser > we can see the default web page 




# Notes:
  3/3 Checks Passed:
     ✔ AWS infrastructure is healthy
     ✔ The instance OS is running correctly
     ✔ Storage and networking are functioning

  IIS -ISS(Internet Information Services) is Microsoft’s web server for hosting and managing web applications on Windows servers.
