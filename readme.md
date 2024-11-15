**Deploying a LAMP Stack on AWS EC2**

Table of Contents
- Introduction
- Launch and Connect to EC2
- Install Apache
- Install MySQL Server
- Install PHP
- Testing the LAMP Stack
- Conclusion



Introduction

The LAMP stack is a widely used open-source web development platform consisting of **Linux, Apache, MySQL, and PHP**. This guide outlines the steps to deploy a LAMP stack on an AWS EC2 instance, complete with code snippets for each step.



1. Launch and Connect to EC2:

Go to the AWS Management Console, Launch an EC2 instance using the **Amazon Linux 2 AMI** with the **t2.micro** instance type. Configure a security group allowing **SSH (port 22)** and **HTTP (port 80)** traffic.

Connect to the instance using the SSH Key pair:

   ```bash
   ssh -i /path/to/key.pem ec2-user@<ipaddress>                # For Amazon Linux 2 AMI
   chmod 400 your-key-pair.pem                                # For Ubuntu Run this command .pem file so only you can read it
  ssh -i /path/to/key.pem ubuntu@your-instance-public-ip     # For Ubuntu
   ```

2.  Install Apache:
   ```bash
  sudo apt update
  sudo apt install apache2 -y
  sudo systemctl start apache2
  sudo systemctl enable apache2
  sudo systemctl status apache2
   ```

3.   Install MySQL Server
   ```bash
   sudo apt install mysql-server -y
   sudo systemctl start mysql
   sudo systemctl enable mysql
   sudo mysql_secure_installation
   ```

4.   Install PHP
   ```bash
   sudo apt update
  sudo apt install php libapache2-mod-php php-mysql -y
  sudo systemctl restart apache2
   ```

5. Testing the LAMP Stack

   Create an index.html page to verify Apache is working.

   ```bash
   sudo nano /var/www/html/index.html
   ```

  Create an info.php page to check if PHP is installed and configured correctly.

   ```bash
   sudo nano /var/www/html/info.php
   
   <?php
      phpinfo();
   ?>
   ```

Conclusion

In these steps, an AWS EC2 instance's basic LAMP stack environment is set up. Using the Apache, MySQL, and PHP components, you may start deploying web applications with this configuration.
