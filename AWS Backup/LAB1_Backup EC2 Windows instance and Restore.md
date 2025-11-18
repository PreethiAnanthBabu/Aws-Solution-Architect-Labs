  AWS Console > EC2 > Create EC2 windows Instance > Advanced details > 
"<powershell>
Install-WindowsFeature -Name Web-Server -IncludeManagementTools
New-Item -Path C:\inetpub\wwwroot\index.html -ItemType File -Value "Hello World Page" -Force
</powershell>" 
> Create Instance > AWS Backup > Vaults > Create new Vault > Dashboard > On-demand backup > Select Resource type > Choose Vault > Select IAM Role > Create On-demand backup
> Vault > Select the Created vault > We can see EC2 instance Id there > Actions > Restore > Now another Instance is created with same name but with different IP
