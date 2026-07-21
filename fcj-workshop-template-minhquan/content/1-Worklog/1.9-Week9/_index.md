---
title: "Week 9 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.9. </b> "
---



### Week 9 Objectives:

* Analyze project requirements and design a 3-tier Cloud architecture.
* Select and choose appropriate AWS services for each architectural layer.
* Build, check, and finalize the Cloud architecture diagram based on feedback from colleagues in the FCAJ group.
* Calculate estimated infrastructure costs.
* Deploy and test core networking and storage components for the project.
* Configure network connections, control traffic, and set up private connections to Amazon S3 and storage resources.

### Tasks to Implement This Week:

| Day | Tasks | Start Date | Completion Date | Reference Material |
| :--- | :--- | :--- | :--- | :--- |
| 1 | Complete the Cloud architecture diagram design following the 3-tier architecture model for the project. | 27/06/2026 | 27/06/2026 | |
| 2 | Analyze project requirements and identify components in the 3-tier Cloud architecture, including the presentation layer, application layer, and data layer. | 28/06/2026 | 28/06/2026 | |
| 3 | Select appropriate AWS services for each architectural layer and build the initial Cloud architecture diagram, including data flow adjustments between components. | 29/06/2026 | 29/06/2026 | |
| 4 | Finalize the Cloud architecture diagram based on reviews and feedback from colleagues in the FCAJ group and calculate total estimated infrastructure costs. | 30/06/2026 | 30/06/2026 | |
| 5 | Deploy core components of the AWS core networking infrastructure for the project. Create and configure an **Amazon VPC**, including required **public subnets, private subnets, and route tables**. Attach an **Internet Gateway** to provide Internet connectivity for public-tier components. Configure **Security Groups** to control inbound and outbound traffic between resources according to the proposed 3-tier architecture. | 01/07/2026 | 01/07/2026 | |
| 6 | Deploy supplementary networking and storage components following the designed Cloud architecture. Configure a **NAT Instance** using an EC2 instance deployed in the public subnet to provide outbound Internet connectivity for resources in the private subnet. Create an **S3 Gateway Endpoint** to allow the VPC to privately connect to Amazon S3 without routing S3 traffic through the public Internet. Configure separate **S3 Buckets** for static website hosting and file uploads to independently manage website content and uploaded data. | 02/07/2026 | 02/07/2026 | |

### Week 9 Achievements:

* Completed the Cloud architecture diagram design following the 3-tier architecture model for the project.
* Analyzed project requirements and identified components in the 3-tier Cloud architecture.
* Selected appropriate AWS services for each architectural layer and built the initial Cloud architecture diagram.
* Finalized the Cloud architecture diagram based on feedback from FCAJ group members and calculated estimated Cloud infrastructure costs.
* Completed the deployment of core networking components, including Amazon VPC, public subnets, private subnets, route tables, Internet Gateways, and Security Groups.
* Deployed a NAT Instance using an EC2 instance in the public subnet to provide outbound Internet connectivity for private subnets.
* Created an S3 Gateway Endpoint for private VPC connectivity to Amazon S3 without public internet routing.
* Configured separate S3 Buckets for static website hosting and file uploads to independently manage website content and uploaded data.
