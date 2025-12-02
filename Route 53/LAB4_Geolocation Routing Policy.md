AWS Console > Create 3 ec2 linux instances in 3 different regions (N.virginia , Ohio , Oregon) > Connect to 3 instances
> Install apache web server and add content
"sudo -i                                  "sudo -i                               "sudo -i  
    yum install httpd -y                   yum install httpd -y                   yum install httpd -y
    service httpd start                    service httpd start                    service httpd start
    cd /var/www/html                       cd /var/www/html                       cd /var/www/html
    echo "N.virginia" >index.html "        echo "Ohio" >index.html "              echo "Oregon" >index.html
> Route 53 > Create hosted zone with the domain > Go daddy > copy the name server from route 53 hosted zone and add in GodaddyNS
> Aws Console > Route 53 > Add record 1(select Geolocation: India → EC2-1 IP)
> Add record 2(select Geolocation: Ireland → EC2-2 IP)
> Add record 3(select Geolocation: Default → EC2-3 IP)
> copy the domain name and paste in browser > Now we can see output from any one of the region based on the geographic location of the DNS query’s SOURCE IP (current public IP), NOT the country where the laptop was purchased.

