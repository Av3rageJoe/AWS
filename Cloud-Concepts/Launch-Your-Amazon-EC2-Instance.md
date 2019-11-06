# **Walkthrough guide for creating an Amazon EC2 instance**

Amazon's Elastic Compute Cloud (EC2) is a web service that allows for resizeable compute capacity in the cloud. This means that applications can be launched without any upfront commitments. It's purpose is to make web-scale cloud computing easier for developers. The EC2 is a web server in the cloud.

### 1. In the Vocareum portal, start a lab and press the AWS button in the top right corner. An AWS Management console should appear
### 2. In the AWS management console, choose the services search bar and search for EC2. Then click Launch Service. This will launch a virtual EC2 server. 

## Choose an Amazon Machine Image (AMI)

The Amazon AMI gives the EC2 the information that it requires to launch the EC2 instance. 

The AMI includes:
  A template for the root volume for the instance, such as an operating system or application server with applications
  Different launch permissions which dictate what AWS users can use the AMI to launch instances
  A device that blocks traffic on an instance. The block device will specify the volumes to attach to each instance when it is launched
  
### 3. Click select for the Amazon Linux 2 AMI (*Note*: in the quickstart list, the most common Amazon AMIs are listed)

Next an instance must be chosen. An instance is a virtual server that applications can be run on. There are a wide range of instance types that are offered by Amazon. Each instance has a differing amount of CPU, memory, storage and entowrking capacity to give the suer flexibility in what they choose. 

### 4. In this instance, a t2.micro will be used. This instance gives 1 CPU and 1 GiB of memory. Once the instance is chosen, click next

## Configure Instance details

The network section indicates what type of Virtual Private Cloud (VPC) you wish to use 

### 9. Set Network to Lab VPC

### 10. Set enable termination protection to protect against accidental termination
When an Amazon EC2 instance is no longer required, it can be terminated. Once terminated, the instance can not be started again. To protect against this happening, the termination protection box is checked.

### 11. Scroll sown to advanced details and enter the following script:

  #!/bin/bash
  yum -y install httpd
  systemctl enable httpd
  systemctl start httpd
  echo '<html><h1>Hello From Your Web Server!</h1></html>' > /var/www/html/index.html
 
The advanced details section allows user data to be passed to the instance. This can be used to perform common automated configuration tasks and run scripts after the instance starts. 
In this case the above bash script will:
  Install an apache web server (httpd)
  Configure the web server to launch on boot
  Activate the web server 
  Create a simple web page
  
### 12. Click next: Add Storage

The Amazon EC2 stores data on a network-attached virtual disk called Elastic Boot Store. 

### 13. Launch the EC2 with 8GiB disk volume. This will be known as the root/boot volume Click Next: Add tags

Tags allow you to categorise your different resources in different ways, such as by purpose, owner or environment.Each tag consists of a key and value. For example, 

### 14. Click Add tag then add: **Key**:*name* **Value**:*Web Server*

### 15. Click Next: Configure Security Group

A security group acts as an instance which controls the traffic for one or more instance. When an instance is launched, one or more ssecurity groups are associated with that instance. Rules are added to the security groups which allow traffic to or from its associated instances

### 16. In configure security group, add the following **Security Group Name**:*Web Server Security Group* **Description**:*Security group for my web browser*

In this exercise, ssh availability to the server will not be accessible. By removing the ability to ssh into the server, the security increases. 

### 17. Deleting the existing SSH rule

### 18. Click review and launch

### 19. Click Launch

The Amazon EC2 uses public key cryptography to encrypt and decrypt login information. In order to log in to the instance, a key pair must be created. Specify the name of the key pair when the instance is launched, and provide the private key when you connect to the instance.
In this lab, the instance will not be logged in to therefore it is not necessary to create a key value pair. However, for future reference this may be necessary.

### 20. Select proceed without keypair option and select the acknowledge box

### 21. Press launch instances

### 22. If successful, a box should appear saying "Your Instances are now launching...". Open the link to access your instance in this box.

![Image of successful instance launch](https://github.com/Av3rageJoe/AWS/blob/master/Images/Your%20instances%20are%20now%20launching.png)

Wait for the web server to display that it is running under the instance state section
