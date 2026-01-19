AWS Console > EC2 > Launch Instance > Give Name , keypair(.pem file), select AMI(Windows) and 
network settings (add rdp and http port from anywhere) > Additional settings > Userdata 
" <powershell>
Install-WindowsFeature -name Web-Server -IncludeManagementTools
New-Item -Path C:\inetpub\wwwroot\index.html -ItemType File -Value "Hello World Page" -Force
</powershell>  "
> once launched give the public ip in browser > we can see the web page > Select the created instance > Actions > Images and templates > Create Image > AMI > select the created AMI > Launch Instance from AMI Image > create Instance > we can see the same output as in the first instance
