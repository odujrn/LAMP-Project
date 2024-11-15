INTRODUCTION

The LAMP stack is a widely used open-source solution for building web servers and applications. It stands for Linux, Apache, MySQL, and PHP. In this guide, I’ll explain the step-by-step process of deploying a LAMP stack on an AWS EC2 instance.


1 .Creating EC2 instances on aws
  And understanding how to connect to my instance remoely via SSH   
     ![PowerShell Log-in](https://github.com/user-attachments/assets/2301b637-186a-4620-b91b-3edc61588e32)



2. Install the Apache server using the following command:
   ![LAMP 101](https://github.com/citadelict/My-devops-Journey/blob/main/LAMP/install%20apache.png)


  ![Apache default page](https://github.com/user-attachments/assets/91baa710-054c-4f45-a166-97f7a0355e66)



3. Install mysql
   sudo apt install mysql-server
   sudo systemctl start mysql
   sudo mysql_secure_installation
  ![install apache mysql](https://github.com/user-attachments/assets/0cda986d-10b5-4c95-acc2-8189851e582b)


  MySQL is  Active and Running
  ![MySQL is  Active and Running](https://github.com/user-attachments/assets/898f1ab5-8609-44c3-9ac8-a2f166ba0709)




4. Install php
   sudo apt install php libapache2-mod-php php-mysql
   sudo systemctl restart apache2

  ![php 8 3 installed and running](https://github.com/user-attachments/assets/29ab8d33-d303-4fb0-8061-4afde8856916)





5. Create a demo index.html page
    sudo nano /var/www/oduamadi/index.html
   
    ![successfull deployed html index page](https://github.com/user-attachments/assets/6b4401d0-4570-412a-bd27-5d0bf549699e)


   Configure apache to render php first before html  

6. Create a basic php.info page to display php version sudo nano /var/www/oduamadi/info.php

![successfull deployed php web page](https://github.com/user-attachments/assets/12d9e164-a89b-4d14-b576-358bf5ff4bb2)

   

