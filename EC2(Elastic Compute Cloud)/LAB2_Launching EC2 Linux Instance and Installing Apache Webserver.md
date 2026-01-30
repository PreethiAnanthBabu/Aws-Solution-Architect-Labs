AWS Console > EC2 > Launch Instance > Give Name , keypair(.ppk file), select AMI(Amazon Linux) and network settings (add ssh and http port from anywhere) > Launch Instance > select the created instance > copy the public IP > Putty > give the public ip as host name > SSH > AUTH > credentials > browse the downloaded ppk file > open > now we are connected to the linux instance > 
> Login as "ec2-user" > Install the apache webserver
  "sudo -i
   yum install httpd -y
   service httpd status
   service httpd start "
> once installed give the public ip in browser > we can see the default web page 



# Notes:
  httpd is the Apache HTTP Server daemon that runs on a system to serve web pages over HTTP/HTTPS.
  -httpd = Apache Web Server
  -Runs as a background service (daemon)
  -Common on Linux systems (Amazon Linux, RHEL, CentOS)
  -Config files usually in /etc/httpd/
  -Default web root: /var/www/html
  
