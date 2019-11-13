# Create an Amazon EBS Snapshot

This walkthrough will show how to create an Amazon EBS Snapshot. It is a follow on from the previous walkthroughs in this repository.

At any point a developer can create a snapshot of their Amazon EBS volumes. These snapshots are stored in the Amazon S3 with high durability. New EBS volumes can then be created from these snapshots for cloning and restoring backups. These screenshots can also be easily shared among other AWS users or regions.

### 1. In the AWS management console, select the volume called "My Volume"

### 2. Under actions, select "Create Snapshot"

### 3. Click Add tag

Configure the tag with the following values:

  **Key:** Name
  **Value:** My Snapshot
  
### 4. Select Create Snapshot, and then Close

### 5. In the left navigation pane, click Snapshots

Your snapshot should be displayed. It will start with a state of *pending* as it is being created, and then will change to a state of *completed*

### 6. In the remote ssh session, delete the file previously created using the command "rm /mnt/data-store/file.txt"

### 7. Verify that the file has been deleted using the command called "ls /mnt/data-store"

A snapshot should have now been created of the EBS volume. The next part of this walkthrough is located under "Restore-the-Amazon-EBS-Snapshot*
