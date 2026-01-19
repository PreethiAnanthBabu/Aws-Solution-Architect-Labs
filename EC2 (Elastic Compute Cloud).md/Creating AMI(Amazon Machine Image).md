AWS Console > EC2 > Launch Instance > Give Name , keypair(.pem file), select AMI(Windows) and 
network settings (add rdp and http port from anywhere) > Additional settings > Userdata 
" <powershell>
Install-WindowsFeature -name Web-Server -IncludeManagementTools
New-Item -Path C:\inetpub\wwwroot\index.html -ItemType File -Value "Hello World Page" -Force
</powershell>  "
> once launched give the public ip in browser > we can see the web page 
