# Hosting-WordPress-on-AWS-EC2
Hosting a Wordpress Website on AWS EC2 which directs to our own DNS


# Project Goal

Goal of my project is to install and host a WordPress website directly on my self-owned domain and the backend will contain all the data and configurations required on AWS Cloud. I will be creating and renting a Virtual computer (AWS EC2), and this will also include installing and configuration all the elements such as Apache2 webserver, DBMS which will be MySQL, and then i will install WordPress. After installing WordPress, I will assign my self-owned domain name to the WordPress website. Whenever someone goes to the domain they will be directed to my WordPress on AWS cloud.


# Architecture Diagram

![image](https://github.com/ankurcyb/Hosting-WordPress-on-AWS-EC2/assets/141453942/0e2b6967-f6ac-40d7-830f-b33b32dd7ba2)


# Terms

## what is a Virtual Computer/Machine ?

A virtual machine (VM) is a digital version of a physical computer. Virtual machine software can run programs and operating systems, store data, connect to networks, and do other computing functions, and requires maintenance such as updates and system monitoring. Virtual computer/machine is AWS EC2 in my case.


## What is AWS EC2?

Amazon Elastic Compute Cloud (Amazon EC2) provides on-demand, scalable computing capacity in the Amazon Web Services (AWS) Cloud. Using Amazon EC2 reduces hardware costs so you can develop and deploy applications faster. You can use Amazon EC2 to launch as many or as few virtual servers as you need, configure security and networking, and manage storage. You can add capacity (scale up) to handle compute-heavy tasks, such as monthly or yearly processes, or spikes in website traffic. When usage decreases, you can reduce capacity (scale down) again.

## What is Apache?

Apache is a Web server, Apache is responsible for accepting directory (HTTP) requests from Internet users and sending them their desired information in the form of files and Web pages. Much of the Web’s software and code is designed to work along with Apache’s features.

## What is MySQL ?

MySQL is the world’s most popular open source database. MySQL ranks as the second-most-popular database and powers many of the most accessed applications, including Facebook, Twitter, Netflix, Uber, Airbnb, Shopify, and Booking.com.

Since MySQL is open source, it includes numerous features developed in close cooperation with users over more than 25 years. So it’s very likely that your favorite application or programming language is supported by MySQL Database.

## What is DNS?

The Domain Name System (DNS) is the phonebook of the Internet.  Humans access information online through domain names, like google.com or youtube.com. Web browsers interact through Internet Protocol (IP) addresses. DNS translates domain names to IP addresses so browsers can load Internet resources.

## What is a SSL Certification?

SSL certificates are what enable websites to use HTTPS, which is more secure than HTTP. An SSL certificate is a data file hosted in a website's origin server. SSL certificates make SSL/TLS encryption possible, and they contain the website's public key and the website's identity, along with related information.

## What is PuTTy? 

PuTTY is a free and open-source terminal emulator, serial console and network file transfer application. It supports several network protocols, including SCP, SSH, Telnet, rlogin, and raw socket connection. It can also connect to a serial port. PuTTY is the recommended application to use for SSH connections from a Windows operating system.


# Technology Used

1. AWS EC2
2. Apache2
3. PHP
4. Shell Scripting
5. MySQL
6. DNS

# Process

1. Creating a Virtual computer
Login to AWS console and navigate to EC2 and click on instance then click on create a instance and choose t2.micro, Ubuntu as  operating system.

![Screenshot 2023-03-22 183049](https://github.com/ankurcyb/Hosting-WordPress-on-AWS-EC2/assets/141453942/629dad2c-eb8c-4125-8daf-4996fa2ae05b)

2. Creating a Key pair
Creating a Key pair in order to login to my virtual computing via SSH and I will be using Putty to login into our virtual computer.

![Screenshot 2024-01-23 154956](https://github.com/ankurcyb/Hosting-WordPress-on-AWS-EC2/assets/141453942/fade642f-bf1e-4e5a-bec9-a7597184b8da)

3. Configuring Network settings and creating Security group
Create security group in order to allow SSH and HTTP traffic in order to login through putty and host it on a website.

![Screenshot 2024-01-23 155043](https://github.com/ankurcyb/Hosting-WordPress-on-AWS-EC2/assets/141453942/c5dd97fe-1e7c-44fe-a445-1980cb008c51)

4. Launch and connect the EC2 instance

![Screenshot 2024-01-23 155149](https://github.com/ankurcyb/Hosting-WordPress-on-AWS-EC2/assets/141453942/8aa396d7-57e0-4447-b0c5-fd38aa66df1b)

5. Associating an Elastic IP to the instance
I will be assigning an elastic to the EC2 instance in order to keep the public IP address of the instance static. So, it is not going to chance everytime it is rebooted. DNS server will store the static IP in order to host website from AWS cloud.

![Screenshot 2024-01-23 155231](https://github.com/ankurcyb/Hosting-WordPress-on-AWS-EC2/assets/141453942/07a5fca5-c88f-42f0-80f2-5901e808edeb)

![Screenshot 2024-01-23 155302](https://github.com/ankurcyb/Hosting-WordPress-on-AWS-EC2/assets/141453942/3765a986-b7d5-4ac7-b52c-5f99bb3c816f)


6. Putty to connect with my virtual computer
This step involves configuring SSH client, Putty in my case according to my EC2 instance and the connect it via command line interface.

![Screenshot 2024-01-23 163224](https://github.com/ankurcyb/Hosting-WordPress-on-AWS-EC2/assets/141453942/f09f0995-6ff0-4d4f-b719-711f0d54d03a)

7. Install Apache Server on instance.

![Screenshot 2024-01-23 163339](https://github.com/ankurcyb/Hosting-WordPress-on-AWS-EC2/assets/141453942/eacf137b-a1ac-4f6b-a08b-814f126a8b12)

8. Checking the website through Public IP.

![Screenshot 2024-01-23 163434](https://github.com/ankurcyb/Hosting-WordPress-on-AWS-EC2/assets/141453942/0e821ede-1545-43ca-a593-aef8a89557a6)

9. Installing PHP on instance
Installing PHP because Wordpress is built on PHP

![Screenshot 2024-01-23 163620](https://github.com/ankurcyb/Hosting-WordPress-on-AWS-EC2/assets/141453942/e8c1b759-7a43-4d0a-a1f1-38ba44089be1)

10. Installing MySQL server for Database

![Screenshot 2024-01-23 163743](https://github.com/ankurcyb/Hosting-WordPress-on-AWS-EC2/assets/141453942/ad31bd2b-a17b-441a-9120-ac1e026c5fb5)

11. Configuring MySQL server
Changing MySQL authentication plugin to a MySQL native password in order to login with a normal password. This is required in order to install Wordpress.

Logging into MySQL prompt
![Screenshot 2024-01-23 164207](https://github.com/ankurcyb/Hosting-WordPress-on-AWS-EC2/assets/141453942/39848fca-4903-415c-a9c6-bb3ec0911db6)

changing authentication plugin and create user and database to use with Wordpress. And granting all privileges to the user on new database. 
![Screenshot 2024-01-23 164655](https://github.com/ankurcyb/Hosting-WordPress-on-AWS-EC2/assets/141453942/c3c5205b-a041-4468-8d53-b9bd2a86d9e8)

12. Installing Wordpress

Get the tar link from the Wordpress website and redirect to cd /tmp directory and download wordpress in the tmp directory.

![Screenshot 2024-01-23 165040](https://github.com/ankurcyb/Hosting-WordPress-on-AWS-EC2/assets/141453942/5b8ad011-e4b2-4267-842d-0c26cbf50a82)

Unzip the file through tar -xvf latest.tar.gz command and then move wordpress to /var/www/html

![Screenshot 2024-01-23 165503](https://github.com/ankurcyb/Hosting-WordPress-on-AWS-EC2/assets/141453942/fbda5d13-df72-4d95-a545-c3aafda08b0b)

13. Checking the webiste
Check the website through the Public IP address followed /wordpress

![Screenshot 2024-01-23 165637](https://github.com/ankurcyb/Hosting-WordPress-on-AWS-EC2/assets/141453942/3655c70c-0ae1-4161-84ee-d9397b558ae3)

14. Installing Wordpress

I Installed the Wordpress, creating username and password followed by all the credential required.

![Screenshot 2024-01-23 165735](https://github.com/ankurcyb/Hosting-WordPress-on-AWS-EC2/assets/141453942/59330aee-b114-4b62-bbf5-03cb2bfcac45)

15. Configuring the PHP file to install Wordpress

Copy the PHP code provided by the Wordpress and create wordpress config file using terminal and paste the code to this file and save it.

![Screenshot 2024-01-23 171112](https://github.com/ankurcyb/Hosting-WordPress-on-AWS-EC2/assets/141453942/454ec8d4-02ac-4c75-a99b-09aafa84a01a)

Come back to browser and run installation, give the site a name and other information neccessary.

![Screenshot 2024-01-23 171336](https://github.com/ankurcyb/Hosting-WordPress-on-AWS-EC2/assets/141453942/48f4fd24-be28-43cc-9c7b-9aeaa055da64)

![Screenshot 2024-01-23 171458](https://github.com/ankurcyb/Hosting-WordPress-on-AWS-EC2/assets/141453942/805fa285-c918-4a6a-a8dc-926d5e47b2b4)


15. Fixing the root path

Currently the Wordpress website is hosted on the subpath directory of my public website. Now, in order to host it directly on the root directory I will configure the Apache2 configuration.

![Screenshot 2024-01-23 171804](https://github.com/ankurcyb/Hosting-WordPress-on-AWS-EC2/assets/141453942/569c8fc1-a1ca-4b65-b0a8-11e3ec91c384)

Adding Wordpress as Root directory

![Screenshot 2024-01-23 172033](https://github.com/ankurcyb/Hosting-WordPress-on-AWS-EC2/assets/141453942/0c707f29-4547-40df-9e86-8319234947e7)

16. Final sample wordpress site.

![Screenshot 2024-01-23 171622](https://github.com/ankurcyb/Hosting-WordPress-on-AWS-EC2/assets/141453942/7626aa4d-2b60-4fb4-8ba9-ed6b6abcaae3)

# Conclusion

Through this project I gained the knowledge how to connect a database which is on of cloud serving as backend and hosting directly on to the website. I will continue editing the root Wordpress website and will create sub directories and connect with AWS S3 to store and host data related to the website.

# Acknowledgement 

This project is inspired by offical AWS documents related to hosting a website.

Link - [https://aws.amazon.com/free/webapps/?gclid=Cj0KCQiAh8OtBhCQARIsAIkWb6_o5TutGkD6Fag2l7b9xkAH-NouaqiRhGECUfkfy3fPKj_mAS7FHu8aAt9rEALw_wcB&trk=0859629e-29af-428f-ab68-152ecf240a0b&sc_channel=ps&ef_id=Cj0KCQiAh8OtBhCQARIsAIkWb6_o5TutGkD6Fag2l7b9xkAH-NouaqiRhGECUfkfy3fPKj_mAS7FHu8aAt9rEALw_wcB:G:s&s_kwcid=AL!4422!3!531871356659!e!!g!!aws%20wordpress%20web%20hosting!11086666988!111455470729](https://aws.amazon.com/getting-started/hands-on/launch-a-wordpress-website/)https://aws.amazon.com/getting-started/hands-on/launch-a-wordpress-website/
