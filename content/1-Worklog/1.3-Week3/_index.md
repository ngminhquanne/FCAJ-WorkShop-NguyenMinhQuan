---
title: "Week 3 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.3. </b> "
---



### Week 3 Objectives:

* Learn how to accelerate static websites on Amazon S3 using Amazon CloudFront.
* Understand advanced networking on AWS with Public Subnets, Private Subnets, NAT Gateways, Route Tables, Security Groups, and Network ACLs.
* Learn how to distribute application traffic using an Application Load Balancer.
* Learn about managed relational databases and high availability with Amazon RDS.
* Learn about the NoSQL storage model with Amazon DynamoDB.
* Learn how Amazon ElastiCache improves application performance by offloading the database.

### Tasks to be carried out this week:
| Day | Tasks | Start Date | Completion Date | Reference Material |
| :--- | :--- | :--- | :--- | :--- |
| 1 | **Explore Amazon CloudFront and CDN**<br>- Learn about CDN, Distribution, Origin, Behavior, Edge Location, and Cache concepts.<br>- Create a CloudFront Distribution with **Amazon S3** as Origin.<br>- Access the S3 static website through CloudFront.<br>- Perform **Cache Invalidation** after updating website content.<br>- Compare direct S3 access with CloudFront access. | 26/05/2026 | 26/05/2026 | [Amazon CloudFront](https://aws.amazon.com/cloudfront/)<br>CloudFront with Amazon S3<br>AWS CloudFront Workshop |
| 2 | **Explore Advanced AWS Networking**<br>- Review Public Subnets and Private Subnets.<br>- Learn about **NAT Gateway, Route Table, Internet Gateway, Security Group, and Network ACL**.<br>- Compare traffic flows between Public Subnets and Private Subnets.<br>- Create a NAT Gateway to allow outbound Internet access for Private Subnets.<br>- Configure routing and verify connectivity.<br>- Distinguish between **Security Groups** and **Network ACLs**. | 27/05/2026 | 27/05/2026 | [Amazon VPC](https://aws.amazon.com/vpc/)<br>[NAT Gateway](https://aws.amazon.com/vpc/nat-gateway/) |
| 3 | **Explore Application Load Balancer**<br>- Learn the role of **Load Balancer** in distributing requests.<br>- Learn about **Application Load Balancer, Listener, Listener Rule, Target Group, and Health Check**.<br>- Create two EC2 Instances as application targets.<br>- Create a Target Group and register the EC2 Instances.<br>- Create an Application Load Balancer across Public Subnets.<br>- Configure the Listener to forward traffic to the Target Group.<br>- Verify traffic distribution and instance health status.<br>- Compare direct EC2 access with Load Balancer access. | 28/05/2026 | 28/05/2026 | Elastic Load Balancing<br>[Application Load Balancer](https://aws.amazon.com/elasticloadbalancing/application-load-balancer/) |
| 4 | **Advanced Amazon RDS Exploration**<br>- Review the role of **Amazon RDS** in relational database management.<br>- Learn about **DB Instance, DB Subnet Group, Security Group, Backup, Snapshot, and Multi-AZ Deployment**.<br>- Create an RDS database in a Private Subnet.<br>- Configure the DB Subnet Group and restrict access using Security Groups.<br>- Connect the application on EC2 to the RDS database.<br>- Create a manual snapshot and restore the database from a snapshot.<br>- Compare Single-AZ and Multi-AZ models.<br>- Check database connectivity and clean up unused resources. | 29/05/2026 | 29/05/2026 | [Amazon RDS](https://aws.amazon.com/rds/)<br>Amazon RDS Multi-AZ deployments<br>Working with DB subnet groups |
| 5 | **Explore Amazon DynamoDB and Amazon ElastiCache**<br>- Learn about the NoSQL model of **Amazon DynamoDB**.<br>- Learn about **Table, Item, Attribute, Partition Key, and Sort Key**.<br>- Create a DynamoDB Table and perform basic **Create, Read, Update, Delete (CRUD)** operations.<br>- Compare DynamoDB with relational databases like Amazon RDS.<br>- Learn the role of **Amazon ElastiCache** in in-memory temporary data storage.<br>- Learn about **Redis** and **Memcached** engines.<br>- Learn how caching offloads the database and improves response times.<br>- Compare application performance with and without a caching layer. | 30/05/2026 | 30/05/2026 | [Amazon DynamoDB](https://aws.amazon.com/dynamodb/)<br>Core components of DynamoDB<br>[Amazon ElastiCache](https://aws.amazon.com/elasticache/)<br>What is Amazon ElastiCache?<br>AWS Workshop 000060<br>AWS Workshop 000061 |


### Week 3 Achievements:

* Successfully create a CloudFront Distribution using Amazon S3 as an Origin and perform cache invalidation.
* Configure advanced VPC networking and understand traffic flow between Public Subnets and Private Subnets.
* Create an Application Load Balancer, configure Target Groups and Listeners, and verify target health status.
* Create an Amazon RDS database within a Private Subnet and practice access control, snapshots, and Multi-AZ concepts.
* Create a DynamoDB Table and perform basic CRUD operations following the NoSQL data model.
* Understand how Amazon ElastiCache, Redis, and Memcached help offload databases and improve response times.
* Distinguish between relational databases, NoSQL databases, and cache memory for different use cases.
