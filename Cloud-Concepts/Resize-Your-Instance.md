# Resize Your Instance: Instance Type and EBS Volume

Naturally over time a developers needs change. Therefore, the instance may need to be changed. With Amazons EC2, this is possible. This tutorial will demonstrate certain aspects that you can change.

## Stop your instance

Before an instance can be resized, it must be stopped. There is no charge for stopping an image, but there is still a charge for the memory used to store the instance.

### 1. On the left hand EC2 Management Console navigation pane, click instances. Select teh desired web server.

### 2. In the actions menu, select Instance state -> stop

### 3. Confirm the stop.

Wait for the instances state to be changed to stopped (signaled by a red dot under Instance State)

## Change the instance Type

### 4. In the actions menu, select Instance Settings -> Change Instance Type

### 5. Then configure **Instance Type**:*t2.small* Click apply.

When the instance is then started again, the instance will have twice as much memory as previous (was t2.micro before)

## Resize the EBS Volume

### 6. In the left navigation menu, click Volumes

### 7. In the actions menu, select Modify Volume

Note that the current volume size is 8GiB

### 8. Change the size to 10 GiB, click modify and confirm

### 9. Click close

## Start the resized image

### 10. In the left navigation pages, click Instances

### 11. Under actions, set Instance State -> start

### 13. Clcik Yes, start

## Explore EC2 Limits

Amazon EC2 provides different resources that you can use. These resources include images, instances, volumes, and snapshots. When you create an AWS account, there are default limits on these resources on a per-region basis.

### 14. In the left navigation pane, select limits

Here the limits can be found and add or deleted.

## Test Termination Protection

At any time you can delete your instance if you no longer need it. Once the instance has been terminated, it can not be connected to nor restarted
This task will teach you how to use temination protection.

### 15. In the actions menu, select Instance state -> terminate

When selected the user is informed that Termination Protection is enabled on the web server. This is to prevent the user accidentally terminating the instance. If the user wants to terminate the server, then they must disable Termination Protection.

### 16. Click Cancel

### 17. In the actions menu, select Instance settings -> Change Termination Protection

### 18. Click Yes, disable

### 19. In the actions menu, select Instance State -> Terminate

### 20. Click yes, terminate. The instance will now have been successfully terminated. 

