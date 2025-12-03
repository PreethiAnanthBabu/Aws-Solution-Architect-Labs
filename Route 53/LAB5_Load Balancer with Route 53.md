AWS Console > EC2 > Create ec2 linux instance > Connect to the Linux instance > Install apache webserver 
 " sudo -i
   yum install httpd -y
   service httpd start 
   cd /var/www/html
   echo "Testing" >index.html "  
> Target groups > create target group for the ec2 instance > Load balancers > create application load balancer > add the       target group to the alb > Route 53 > Create a hosted zone with the domain created in Go daddy > GO Daddy > add the AWS Route 53 name servers into GoDaddy > AWS Console > Route 53 > Create Record > enable alias > choose alb > choose region where the ec2 is created > choose the created load balancer > create record > now give the domain name in browser
