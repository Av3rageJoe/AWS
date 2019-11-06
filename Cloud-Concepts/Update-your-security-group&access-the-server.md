# Update Your security group and Access the web server

This tutorial is a follow on from Launch Your Amazon EC2 Instance & Monitor Your Instance. In order to complete this tutorial, follow the other tutorials first.

When the EC2 script was first launched, a script was provided to install a webserver and create a basic HTML page. In this tutorial, the content from within the web server will be accessed.

### 1. Click the Description tab on the instances page.

### 2. Copy your IPv4 address of your instance

### 3. Open a new tab and paste it into the web browser. 

You will be unable to access the webserver like this. Although you should be able to. Why is this?

You are not currently able to access your web server because the security group is not permitting inbound traffic on port 80, which is used for HTTP web requests. This is a demonstration of using a security group as a firewall to restrict the network traffic that is allowed in and out of an instance.

In order to correct this, the security groups rules will need to be modified.

### 4. Return to the EC2 Management console

### 5. In the navigation bar on the left, select Security Groups

### 6. Select Web Server security group

### 7. Click the Inbound tab

### 8. Click edit, then configure: **Type**:*HTTP* **Source**:*Anywhere* Then click save

This will now add the rule to allow for HTTP traffic to the web server from anywhere 

### 9. Reload the web server. The page should now load successfully.
