---
title: "Week 6 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.6. </b> "
---



### Week 6 Objectives:

* Understand the role of AWS Security Hub and Amazon GuardDuty in AWS security monitoring.
* Protect web applications using AWS WAF.
* Implement user authentication and authorization using Amazon Cognito.
* Explore container deployment with Amazon ECR and Amazon ECS.
* Deploy containerized applications using AWS Fargate.

### Tasks to Implement This Week:

| Day | Tasks | Start Date | Completion Date | Reference Material |
| :--- | :--- | :--- | :--- | :--- |
| 1 | **Explore AWS Security Hub and Amazon GuardDuty**<br>- Learn about security posture, findings, and security standards.<br>- Enable Security Hub and check security findings.<br>- Enable GuardDuty and learn about threat detection mechanisms.<br>- Compare the roles of Security Hub and GuardDuty. | 11/06/2026 | 11/06/2026 | [AWS Security Hub](https://aws.amazon.com/security-hub/)<br>[Amazon GuardDuty](https://aws.amazon.com/guardduty/) |
| 2 | **Explore AWS WAF**<br>- Learn about Web ACL, Rule, Rule Group, Managed Rules, and Rate-Based Rules.<br>- Create a Web ACL and associate it with a CloudFront Distribution or Application Load Balancer.<br>- Test allowed and blocked requests.<br>- Check WAF metrics and logs. | 12/06/2026 | 12/06/2026 | [AWS WAF](https://aws.amazon.com/waf/)<br>What is AWS WAF? |
| 3 | **Explore Amazon Cognito**<br>- Learn about User Pool, Identity Pool, user, group, and JWT tokens.<br>- Create a User Pool and configure user sign-in.<br>- Learn authentication and authorization flows.<br>- Protect APIs using Cognito tokens. | 13/06/2026 | 13/06/2026 | [Amazon Cognito](https://aws.amazon.com/cognito/)<br>What is Amazon Cognito? |
| 4 | **Explore Amazon ECR and Amazon ECS**<br>- Learn about container image, repository, cluster, task, Task Definition, and Service.<br>- Create an Amazon ECR Repository.<br>- Push application images to ECR.<br>- Create an ECS Cluster and configure Task Definitions.<br>- Deploy an ECS Service using images from ECR. | 14/06/2026 | 14/06/2026 | [Amazon ECR](https://aws.amazon.com/ecr/)<br>[Amazon ECS](https://aws.amazon.com/ecs/) |
| 5 | **AWS Fargate Hands-on Lab**<br>- Deploy container images from ECR to ECS using **AWS Fargate**.<br>- Configure the ECS Service and check health status.<br>- Connect the service to an Application Load Balancer.<br>- Access containerized applications and check CloudWatch Logs.<br>- Delete ECS, Fargate, ECR, and load balancer resources after completion. | 15/06/2026 | 15/06/2026 | [AWS Fargate](https://aws.amazon.com/fargate/)<br>Getting started with Amazon ECS |

### Week 6 Achievements:

* Enabled and checked security findings using AWS Security Hub as well as threat detections using Amazon GuardDuty.
* Created AWS WAF Web ACLs and tested request filtering rules.
* Created Amazon Cognito User Pools and understood token authentication mechanisms.
* Created Amazon ECR Repositories and managed container images.
* Created Amazon ECS Clusters, Task Definitions, and Services.
* Deployed containerized applications to AWS Fargate and accessed them via Application Load Balancers.
* Practiced checking logs, verifying resource health statuses, and cleaning up AWS resources.
