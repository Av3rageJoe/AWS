# Restore the Amazon EBS Snapshot

If you ever wish to retrieve the data from a snapshot, you can restore the snapshot to a new EBS volume

## Create a Volume using your snapshot

### 1. In the AWS management console, select "My Snapshot"

### 2. In the actions menu, Click Create Volume

### 3. For Availabilty zone, select teh same availability zone as earlier

### 4. CLick "Add Tag"

Configure the tage with the follwoing values:

**Key:** Name
**Value:** Restored Volume

Then press "Create Volume", followed by "Close"

Note: When restoring a snapshot to a new volume, you can also modify the configuration, such as changing the volume type, size or Availability Zone.

## Attach the Restored Volume to Your EC2 Instance

### 5. In the left navigation pane, select Volumes

### 6. Select Restored Volume

### 7. In the actions menu, click Attach Volume

### 8. Click the instance section and select the instance thats called "Lab"

Note that this instance is saved to */dev/sdg*. This will be used later

### 9. Click Attach

The volume state should now be "in-use"

## Mount the Restored volume

### 10. Using the ssh session, create a mounting point for the restored volume

You can do this by running the command **sudo mkdir /mnt/data-store2**

### 11. Mount the new volume

Mount the volume by running the command **sudo mount /dev/sdg /mnt/data-store2**

### 12. Verify that the volume mounted has the file that was created earlier.

Previously, the file "file.txt" was deleted from the volume. Under the restored volume however, this file should be seen again. Verify that this is the case by running the command **ls /mnt/data-store2**
