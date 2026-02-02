AWS Console > EC2 > Launch Instance > Give Name , keypair(.pem file), select AMI(Windows) and 
network settings (add rdp and http port from anywhere) > Additional settings > Userdata 
" <powershell>
Install-WindowsFeature -name Web-Server -IncludeManagementTools
New-Item -Path C:\inetpub\wwwroot\index.html -ItemType File -Value "Server 1" -Force
</powershell>  " 
AWS Console > EC2 > Launch Instance in diff availability zone > Give Name , keypair(.pem file), select AMI(Windows) and 
network settings (add rdp and http port from anywhere) > Additional settings > Userdata 
" <powershell>
Install-WindowsFeature -name Web-Server -IncludeManagementTools
New-Item -Path C:\inetpub\wwwroot\index.html -ItemType File -Value "Server 2" -Force
</powershell>  "
Load Balancer > Create Classic load balancer > Give name , select atleast 2 availability zones, health checks , add the created instances
> Now copy the load balancer endpoint of the load balancer and give it in browser > we can see the web page coming from different instances consecutively 
