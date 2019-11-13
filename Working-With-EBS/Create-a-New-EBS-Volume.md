# Create a New EBS Volume

In this task, an EBS volume will be created and attached to an EC2 instance.

Use Vocareum, an AWS Lab was started, which directed the user to the AWS management console. 

### 1. On the AWS Management console, under services, search for EC2

### 2. Choose the instances option in the left navigation pane

If not already done so, create an instance called Lab. If you are unsure how to do so, please refer to the Cloud-Concepts repository under AWS. 

Take note of the availability zone that the instance is located under. 

### 3. In the left navigation pane, click Volumes

### 4. Click Create Volume

Configure the volume with the following settings

  **Volume Type:** General Purpose SSD (gp2)
  **Size(GiB):** 1
  **Availability Zone:** Select the same availability zone as the one seen under the created instance.

**Click Add tag**
  
   In the tag editor enter:
   
      **Key:** Name
      **Value:** My Volume
   
### 5. Click Create Volume, then Close

Once these steps have been completed, the EBS will be created. The next part of this walk through is *Attach a volume to an Instance*
