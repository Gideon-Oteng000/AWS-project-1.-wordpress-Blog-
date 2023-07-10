# HOW I HOSTED MY WORDPRESS BLOG ON AWS [DEONCLOUD.COM](https://deoncloud.com "Deoncloud blog")
--- 

## ALL THE AWS SERVICES I USED 
- EC2 (Virtual Server)
- ROUTE 53 (DNS Web Services)
- Application Load Balancer (traffic load balancing)
- Auto Scaling Group (Scaling EC2 instances to meet traffic demands)
- S3 bucket (for object storage)
- Cloudfront (for global content delivery)
- AWS WAF (Web App Firewall)
- RDS (Mysql for database)

---

## STEPS 

1. Purchased the domain name in Route 53
2. Launched an ec2 instance (t2 micro, Amazon Linux)
   - configure the security group inbound rule of the ec2 instance to allow ssh on port 22, http on port 80 and https on port 443

3. Installed the LAMP stack on the ec2 instance 
   ```bash 
   # connecting to ec2 instance
   ssh -i <path-to-your-key-pair> ec2-user@<your-instance-public-ip>

   # updating the system packages 
   sudo yum update -y

   # Install the apache webserver
   sudo yum install -y httpd

   # install PHP
   sudo yum install -y php 

   # install additional PHP extension
   sudo yum install -y php-mysqlnd

   #install the database 
   sudo yum install Mariadb105-server Mariadb-client

   # start the server
   sudo systemctl start httpd 
   sudo systemctl enable httpd

   # add the ec2-user to the 'apache' group on the Linux system
   sudo usermod -a -G apache ec2-user

   # recursively change the ownership of all files and directories within /var/www to the user ec2-user and the group apache. 
   sudo chown -R ec2-user:apache /var/www
   
   # allowing the owner and group to have full read, write, and execute access.
   sudo chmod 2775 /var/www
   find /var/www -type d -exec sudo chmod 2775 {} +
   find /var/www -type f -exec sudo chmod 0664 {} +

   ```

4. Set up Mysql database for Wordpress 
   ```bash
   sudo mysql -u root
   CREATE DATABASE wordpress;
   CREATE USER 'wordpress'@'localhost' IDENTIFIED BY 'your_password';
   GRANT ALL PRIVILEGES ON wordpress.* TO 'wordpress'@'localhost';
   FLUSH PRIVILEGES;
   EXIT;
   ```
5. Download and configure Wordpress
   ```bash
   cd /var/www/html
   sudo wget https://wordpress.org/latest.tar.gz
   sudo tar -xzf latest.tar.gz
   sudo mv wordpress/* .
   sudo rm -rf wordpress latest.tar.gz
   sudo chown -R apache:apache /var/www/html

   ```
6. Run your ec2 instance public IP in browser to check if all the Installation worked. If it worked, You will see a wordpress webpage asking you to connect to your database. 

---
   
###  NOW THAT YOUR WORDPRESS WEBSITE IS WORKING, IT IS TIME TO SCALE OUR WORDPRESS WEBSITE  
1. Now on your EC2 instance dashboard, create a target group with the ec2 instance as a target. 
   
2. Create an application load balancer. Configure the ALB listener to listen to listen on port 80 and foreard traffic to the target group 
3. Run the ALB DNS name in the browser. If the wordpress page apppears that mean it is working.
4. Request for an SSL certificate in ACM. The name should be the same as the name you bought in Route 53.
   
5. Configure Cloudfront with the ALB as the origin. 
   - In the origin protocol, select Http port only
   - In the settings, under the alternate domain name, type out the domain name I bought in Route 53
   - Under custom SSL certificate, select the SSL certificate you requested in ACM.
   - Enable AWF WAF in Cloudfront.
  


