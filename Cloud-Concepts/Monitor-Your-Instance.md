# Monitor Your Instance

This walkthrough is a follow on from Launch Your Amazon EC2 Instance. If the previous walkthrough has not been completed  then it is reccommended to complete that walkthrough first

Monitoring your instance is an important part of maintaing the reliability and availability and performance of your EC2.

### 1. Click the status checks tab

Instance status montioring provides an easy way to detect any problems that might prevent your instance from running applications.
Amazon EC2 automatically performs regular checks on all instances to detect hardware and/or software issues.

### 2. Click the monitoring tab

In this tab you can view the Amazon CloudWatch metrics for your instance. Amazon EC2 automatically sends metrics to Amazon CloudWatch for your instances.

### 3. In the actions menu, select Instance settings -> Get System Log
This displays the console output log for the instance, which can prove valuable when diagnosing a problem. It is especially useful for troubleshooting kernel problems and service configuration issues
Scrolling through the output, the http page that was designed to be setup on install can be seen

### 4. In the actions menu, select instance settings -> get instance screenshot

This page shows you what the EC2 instance would look like if viewed from a console


That is the end of this tutorial. It was designed to show you a bit on how to navigate around and view your instance.
