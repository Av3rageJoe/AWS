# READ ME

This folder contains a walkthrough on how to:

  1. Create an Amazon EBS account
  2. Attach and mount your volume to an EC2 instance
  3. Create a snapshot of your volume
  4. Create a new volume from your snapshot
  5. Attach and mount the new volume to your EC2 instance

## What is an EBS?

The EBS is Amazons Elastic Block Store. This is a key underlying storage mechanism for Amazons EC2 instances. Amazon EBS volumes persist independently from the life of an instance. Therefore if an instance is destroyed, the EBS would not be.

The EBS volumes are highly available, and are reliable instances that can be used as an EC2 boot partition or attached to a running EC2 instance as a standard block device.

When the EBS is used as a boot partition, EC2 instances can be stopped and then restarted. This allows you to only pay for the storage resources used while maintaining your instances state.

Another benefit of using an EBS over individual EC2s is that their is improved durability because the EBS volumes are automatically copied on the back end (in a single availability zone).

If further durability is wanted, then Amazon allows for point-in-time snapshots to be created and stored in the Amazon S3 (Simple Storage Service), and then automatically copied across multiple availability zones. The snapshots can then be used as a starting point for new EBS volumes and they can protect your data for long term durability. 

## EBS volume features

  1. Persistent storage - A volumes lifetime is independent of any individual EC2 instance created on it.
  2. General Purpose - The EBS volumes are raw and unformatted block devices which then allow for use by any operating system.
  3. High Performance - The EBS volumes are all either equal to, or better than the local EC2 drives.
  4. High reliability - All EBS volumes have built in redundancy within the availability zones. 
  5. Designed for resiliency - The Annual Fail Rate (AFR) of Amazons EBS is between 0.1% and 1%
  6. Variable size - Volumes can range from as little as 1GB to as much as 16 TB
  7. Easy to use - EBS volumes can easily be created, backed up, attached, restored and deleted. 
