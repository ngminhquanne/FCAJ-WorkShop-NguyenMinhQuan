---
title: "Week 10 Worklog"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.10. </b> "
---



### Week 10 Objectives:

* Deploy the application layer and database layer according to the Cloud architecture.
* Configure managed database, compute, load balancing, and asynchronous messaging services.
* Establish integration flows between S3 Event Notifications and SQS.

### Tasks to Implement This Week:

| Day | Tasks | Start Date | Completion Date | Reference Material |
| :--- | :--- | :--- | :--- | :--- |
| 1 | Deploy an RDS DB Subnet Group and RDS PostgreSQL in private subnets to provide the database layer for the application. | 03/07/2026 | 03/07/2026 | |
| 2 | Deploy EC2 Application Servers in the application layer and configure connections to the PostgreSQL database. | 04/07/2026 | 04/07/2026 | |
| 3 | Deploy an Application Load Balancer to distribute requests to the application servers and monitor target instance health status. | 05/07/2026 | 05/07/2026 | |
| 4 | Create an SQS Queue and a Dead-Letter Queue (DLQ) to support asynchronous message processing and store messages that fail to process successfully. | 06/07/2026 | 06/07/2026 | |
| 5 | Configure S3 Event Notifications to send events from the S3 Bucket to the SQS Queue when a file upload activity occurs. | 07/07/2026 | 07/07/2026 | |

### Week 10 Achievements:

* Deployed an RDS DB Subnet Group and RDS PostgreSQL in private subnets.
* Deployed EC2 Application Servers and configured connections to the PostgreSQL database.
* Deployed an Application Load Balancer to distribute requests to application servers.
* Created an SQS Queue and a Dead-Letter Queue (DLQ) for asynchronous processing.
* Configured S3 Event Notifications to send file upload events to the SQS Queue.
