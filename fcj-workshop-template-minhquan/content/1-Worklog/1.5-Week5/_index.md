---
title: "Week 5 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.5. </b> "
---



### Week 5 Objectives:

* Securely manage secrets using AWS Secrets Manager and AWS KMS.
* Describe and deploy AWS resources using CloudFormation code.
* Build and test source code using AWS CodeBuild.
* Automate the build and deployment process with AWS CodePipeline.
* Build a CI/CD pipeline for the serverless application developed in Week 4.

### Tasks to Implement This Week:

| Day | Tasks | Start Date | Completion Date | Reference Material |
| :--- | :--- | :--- | :--- | :--- |
| 1 | **Explore AWS Secrets Manager and AWS KMS**<br>- Learn how to securely store database credentials, API keys, and application secrets.<br>- Create and retrieve secrets using IAM permissions.<br>- Learn about data encryption at rest using AWS KMS.<br>- Replace hard-coded credentials with runtime secret retrieval mechanisms. | 06/06/2026 | 06/06/2026 | [AWS Secrets Manager](https://aws.amazon.com/secrets-manager/)<br>[AWS KMS](https://aws.amazon.com/kms/)<br>Workshop AWS 000096<br>Workshop AWS 000033 |
| 2 | **Explore AWS CloudFormation**<br>- Learn about Template, Stack, Parameter, Output, Resource, and Change Set.<br>- Write a basic YAML template.<br>- Deploy and update AWS resources via CloudFormation Stack.<br>- Delete Stack and verify resource cleanup. | 07/06/2026 | 07/06/2026 | [AWS CloudFormation](https://aws.amazon.com/cloudformation/)<br>How CloudFormation Works<br>Workshop AWS CloudFormation |
| 3 | **Explore AWS CodeBuild**<br>- Learn about build project, source configuration, environment, build phases, and artifacts.<br>- Create a `buildspec.yml` file.<br>- Run build and test commands.<br>- Inspect build logs and generated artifacts. | 08/06/2026 | 08/06/2026 | [AWS CodeBuild](https://aws.amazon.com/codebuild/)<br>Build commands<br>Workshop AWS 000023 |
| 4 | **Explore AWS CodePipeline**<br>- Learn about Source, Build, Deploy, Stage, Action, and Pipeline.<br>- Connect a source repository to CodePipeline.<br>- Add CodeBuild as the build stage.<br>- Inspect pipeline execution and error handling methods. | 09/06/2026 | 09/06/2026 | [AWS CodePipeline](https://aws.amazon.com/codepipeline/)<br>CodeBuild with CodePipeline<br>Workshop AWS 000023 |
| 5 | **CI/CD Hands-on Lab**<br>- Build a pipeline for the **API Gateway -> Lambda -> DynamoDB** architecture.<br>- Use CodeBuild to inspect source code.<br>- Use CloudFormation to create or update resources.<br>- Store sensitive configurations in Secrets Manager.<br>- Verify deployment via API requests and CloudWatch Logs.<br>- Clean up temporary resources after completing the lab. | 10/06/2026 | 10/06/2026 | [AWS CodePipeline](https://aws.amazon.com/codepipeline/)<br>AWS Serverless Workshops |

### Week 5 Achievements:

* Securely stored and retrieved application secrets using AWS Secrets Manager and understood the role of AWS KMS.
* Created CloudFormation templates and deployed AWS resources via Stacks.
* Configured AWS CodeBuild to run builds, tests, and generate artifacts.
* Created CodePipeline with source and build stages.
* Completed the CI/CD Hands-on Lab for the serverless application using API Gateway, Lambda, DynamoDB, CloudFormation, CodeBuild, and CodePipeline.
* Practiced checking build logs, verifying deployments, checking IAM permissions, and cleaning up AWS resources.