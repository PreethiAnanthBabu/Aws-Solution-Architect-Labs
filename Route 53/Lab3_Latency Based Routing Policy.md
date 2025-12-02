AWS Console > Create 3 ec2 linux instances in 3 different regions (N.virginia , Ohio , Oregon) > Connect to 3 instances
> Install apache web server and add content
"sudo -i                                  "sudo -i                               "sudo -i  
    yum install httpd -y                   yum install httpd -y                   yum install httpd -y
    service httpd start                    service httpd start                    service httpd start
    cd /var/www/html                       cd /var/www/html                       cd /var/www/html
    echo "N.virginia" >index.html "        echo "Ohio" >index.html "              echo "Oregon" >index.html
> Route 53 > Create hosted zone with the domain > Go daddy > copy the name server from route 53 hosted zone and add in GodaddyNS
> Aws Console > Route 53 > Add record 1(select latency based policy and select the region where instance 1 is created)
> Add record 2(select latency based policy and select the region where instance 2 is created)
> Add record 3(select latency based policy and select the region where instance 3 is created)
> copy the domain name and paste in browser > Now we can see output from any one oF the region based on latency
