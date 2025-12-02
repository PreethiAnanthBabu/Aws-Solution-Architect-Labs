AWS Console > Create 2 Linux Instances > Connect to 2 EC2 instances > Install Apache webserver in both isntances 
> Add different contents in both linux instances
   "sudo -i                                                  "sudo -i
    yum install httpd -y                                      yum install httpd -y
    service httpd start                                       service httpd start
    cd /var/www/html                                          cd /var/www/html
    echo "Server1 is responding" >index.html "                echo "Server2 is responding" >index.html "
> Route 53 > Create hosted Zone with the domain name created in go daddy > Go daddy > Add name servers of route 53 in godaddy
> Route 53 > Create health check for instance 1 > create record for instance 1( Select failover routing policy and primary in failover record type) > create record for instance 2( Select failover routing policy and secondary in failover record type)  
> Now browse the domain name , we can see the response from instance 1 > EC2 > Stop primary instance > Now browse the domain name , we can see the response from instance 2(secondary instance) 

