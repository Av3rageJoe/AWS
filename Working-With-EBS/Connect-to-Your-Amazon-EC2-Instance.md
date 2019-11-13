# Connect to You Amazon EC2 Instance

In order to connect to the EC2, you will need to be able to SSH into the server. MacOS and Linux users can do this via the command line. If on a Windows device, then a program will need to be installed in order to allow for SSH access. The recommended program is Putty.exe and can be found here: https://www.putty.org

### 1. In Vocareum, select the details button (top right) followed by show

### 2. Then select the download PEM file. This will downlaod a file that will become the public key needed to SSH into the Instance.

### 3. Navigate to where the file was downloaded on the terminal and run the command *chmod 400labsuser.pem*

Running this command will change the permissions of the file so that only the root user can read the file. 

### 4. Select instances from the left navigation pane of the AWS Management Console

### 5. Select the "Lab" instance and copy the IPv4 address located under "Description"

### 6. Run the command ssh -i labsuser.pem ec2-user@<IPv4 ADDRESS>
  
Where the "IPv4 ADDRESS" section is replaced with the IPv4 address of the Instance

If successful, then you should have successfully connected to the EC2 instance via ssh

The next walkthrough is *Create-and-Configure-a-File-System*
