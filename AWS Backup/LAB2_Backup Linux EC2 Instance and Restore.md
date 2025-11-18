AWS Console > EC2 > Create EC2 Linux Instance > Connect to the Linux Instance > Install Apache webserver 
" sudo -i 
  yum install httpd -y
  service httpd start "
AWS Backup > Vaults > Create new Vault > Dashboard > On-demand backup > Select Resource type > Choose Vault > Select IAM Role > Create On-demand backup 
> Vault > Select the Created vault > We can see EC2 instance Id there
> Actions > Restore > Now another Instance is created with same name but with different IP > Connect to the newly created EC2 Linucx instance and start the httpd webserver
