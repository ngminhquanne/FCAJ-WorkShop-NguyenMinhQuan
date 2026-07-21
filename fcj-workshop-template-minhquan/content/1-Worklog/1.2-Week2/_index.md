---
title: "Week 2 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.2. </b> "
---



### Week 2 Objectives:

* Gain an in-depth understanding of the virtual machine model on AWS through Amazon EC2.
* Understand EC2 instance components such as AMI, Instance Type, Key Pair, and Security Group.
* Practice connecting and managing servers using SSH and AWS Systems Manager Session Manager.
* Learn about auto-scaling mechanisms with EC2 Auto Scaling.
* Get familiar with the simple server service Amazon Lightsail.
* Learn about storage services on AWS including Amazon EBS, Amazon S3, and Amazon EFS.
* Practice creating, attaching, managing, and backing up storage resources on AWS.

### Tasks to be carried out this week:
| Day | Tasks | Start Date | Completion Date | Reference Material |
| :--- | :--- | :--- | :--- | :--- |
| 1 | **Explore Amazon EC2 and Compute VM**<br>- Learn about Virtual Machine and EC2 Instance concepts.<br>- Learn about AMI, Instance Type, Key Pair, and Security Group.<br>- Learn about the lifecycle of an EC2 Instance.<br>- Distinguish between Public IP, Private IP, and Elastic IP. | 20/05/2026 | 20/05/2026 | [Amazon EC2](https://aws.amazon.com/ec2/)<br>[Introduction to Amazon EC2](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts.html) |
| 2 | **Deploy and Access EC2 Instance**<br>- Create an EC2 Instance from an AMI.<br>- Configure Instance Type, Key Pair, and Security Group.<br>- Connect to EC2 via SSH.<br>- Create an IAM Role for EC2.<br>- Grant AmazonSSMManagedInstanceCore permission to the Role.<br>- Attach the IAM Role to the EC2 Instance.<br>- Check the status of the SSM Agent.<br>- Access and manage EC2 via AWS Systems Manager Session Manager.<br>- Compare SSH and SSM access methods. | 21/05/2026 | 21/05/2026 | [Amazon EC2](https://aws.amazon.com/ec2/)<br>[AWS Systems Manager](https://aws.amazon.com/systems-manager/)<br>[Introduction to Amazon EC2](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts.html) |
| 3 | **Explore EC2 Auto Scaling and Amazon Lightsail**<br>- Learn about Launch Template and Auto Scaling Group.<br>- Distinguish between Minimum Capacity, Desired Capacity, and Maximum Capacity.<br>- Learn about Scaling Policy and Health Check.<br>- Create an Amazon Lightsail Instance.<br>- Configure Static IP and Firewall Rules in Lightsail. | 22/05/2026 | 22/05/2026 | [EC2 Auto Scaling](https://aws.amazon.com/ec2/autoscaling/)<br>[Amazon Lightsail](https://aws.amazon.com/lightsail/)<br>[Deploying FCJ Management app with Auto Scaling Group](https://aws.amazon.com/)<br>[Amazon Lightsail Workshop - Cost Optimization on AWS](https://aws.amazon.com/) |
| 4 | **AWS Storage Foundation (Amazon S3)**<br>- Learn about Object Storage model and architecture of Amazon S3.<br>- Learn about Bucket, Object, Object Key, and Region.<br>- Create and configure an S3 Bucket.<br>- Practice upload, download, copy, and delete Object.<br>- Configure Static Website Hosting on Amazon S3.<br>- Learn about Cross-Origin Resource Sharing (CORS) and configure CORS Policy for frontend to access S3.<br>- Learn about Storage Class, Versioning, Lifecycle Rule, and Server-Side Encryption.<br>- Learn about Block Public Access, Bucket Policy, and IAM Policy permission.<br>- Practice S3 management via AWS Management Console and AWS CLI. | 23/05/2026 | 23/05/2026 | [Amazon S3](https://aws.amazon.com/s3/)<br>[Hosting static website with Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/userguide/WebsiteHosting.html)<br>[S3 Static Website Hosting](https://aws.amazon.com/)<br>[S3 CORS](https://docs.aws.amazon.com/AmazonS3/latest/userguide/cors.html) |
| 5 | **Explore S3 Access Point, Storage Classes, and Data Lifecycle**<br>- Learn about S3 Access Point and how to create private access points for specific applications or user groups.<br>- Learn about S3 Storage Classes and selection criteria based on data access frequency.<br>- Learn about S3 Lifecycle Rule to automatically transition or delete Objects over time.<br>- Learn about cold storage services (Cold Storage) such as S3 Glacier Instant Retrieval, S3 Glacier Flexible Retrieval, and S3 Glacier Deep Archive.<br>- Compare retrieval times, minimum storage duration, and costs among S3 Glacier Storage Classes.<br>- Practice configuring S3 Access Point, Lifecycle Rule, and verify the Storage Class transition process. | 24/05/2026 | 24/05/2026 | [Amazon S3 Access Points](https://docs.aws.amazon.com/AmazonS3/latest/userguide/access-points.html)<br>[S3 Storage Classes](https://aws.amazon.com/s3/storage-classes/)<br>[S3 Lifecycle](https://docs.aws.amazon.com/AmazonS3/latest/userguide/object-lifecycle-mgmt.html) |
| 6 | **Explore Amazon EFS and Practical Summary**<br>- Learn about File Storage model of Amazon EFS.<br>- Create an EFS File System and Mount Target.<br>- Connect EFS to an EC2 Instance.<br>- Test the ability to read and write data on EFS.<br>- Compare EBS, S3, and EFS.<br>- Clean up unused resources after practice. | 25/05/2026 | 25/05/2026 | [Amazon EFS](https://aws.amazon.com/efs/) |


### Week 2 Achievements:

* Deploy and manage EC2 Instances, IAM Roles, SSH, and SSM.
* Understand and practice EC2 Auto Scaling and Amazon Lightsail.
* Create, attach, and back up EBS Volumes.
* Manage S3 Buckets, Objects, Static Website Hosting, and CORS.
* Understand S3 Access Points, Storage Classes, Lifecycle Rules, and Cold Storage.
* Connect and use Amazon EFS with EC2.
* Distinguish between Block Storage, Object Storage, and File Storage.
