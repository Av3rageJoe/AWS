# Create and Configure a File System

This guide will explore how to Create and Configure a file system on EBS.

The EC2 instance must be ssh'd into in order to complete this lab. 

### 1. Run the df -h command to view the storage available on the instance.

The result should be something similar to the following:

![Storage available on an instance](https://github.com/Av3rageJoe/AWS/blob/master/Images/Screenshot%202019-11-13%20at%2015.59.03.png)

This shows the original volume created, and not the 1GB volume created earlier.

### 2. Create an ext3 filesystem on the new volume

Run the command **sudo mkfs -t ext3 /dev/sdf**

Note: the path to your volume may be different. A note should have been taken in the previous tutorials of the path.

### 3.Create a directory to mount the new storage volume to

Run the command **sudo mkdir /mnt/data-store** to create a directory called data-store where the volume will be mounted to.

### 4. Mount the volume

Mount the volume by running the command  **mount /dev/sdf /mnt/data-store**

In order to configure the linux instance to mount this device every time it is launched, a command will need to be entered in to the /etc/fstab file. To do so, run the following command: **echo "/dev/sdf   /mnt/data-store ext3 defaults,noatime 1 2" | sudo tee -a /etc/fstab**

### 4. Confirm the command has been entered successfully by running the command "*cat /etc/fstab*"

### 5. View the available data storage again to show that a new storage location has now been included

Run the command **df -h**

The storage can be seen called "xvdf":

![The added data storage location](https://github.com/Av3rageJoe/AWS/blob/master/Images/Screenshot%202019-11-13%20at%2016.11.14.png)

### 6. On the mounted volume, create a file and add some text to it

Run the command **sudo sh -c "echo some text has been written > /mnt/data-store/file.txt"**

This will create a text file in the new file called "file.txt" with the contents "some text has been written" contained within

### 7. Verify the file has been added with its contents by running the command "*cat /mnt/data-store/file.txt*"

A file system should now have been created on the Instance. The next part of this tutorial can be found under *Create-an-Amazon-EBS-Snapshot*
