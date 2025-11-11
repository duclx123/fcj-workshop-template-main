---
title: "Week 9 Worklog"
date: 2025-11-03
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Week 9 Objectives:

* Learn how to design secure and scalable CI/CD pipelines.  
* Build deployment workflows using **AWS CodePipeline**, **CodeBuild**, and **CodeDeploy**.  
* Integrate GitHub or CodeCommit as the source provider.  
* Automate application deployment to EC2 and Lambda.  
* Strengthen pipeline security and add automated testing stages.  

---

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
|-----|------|-------------|------------------|--------------------|
| 2 | - Study concepts of **CI/CD pipelines** on AWS.<br>- Understand how CodePipeline orchestrates build → test → deploy.<br>- **Practice:**<br>&emsp;+ Create a simple CodePipeline with GitHub as the source.<br><br>→ Gain foundational understanding of CI/CD automation. | 03/11/2025 | 03/11/2025 | [AWS Study Group](https://000042.awsstudygroup.com/) |
| 3 | - Learn **AWS CodeBuild** for building and testing applications.<br>- **Practice:**<br>&emsp;+ Write a `buildspec.yml` file.<br>&emsp;+ Run automated builds and unit tests.<br><br>→ Understand build automation and environment configuration. | 04/11/2025 | 04/11/2025 | [AWS Study Group](https://000043.awsstudygroup.com/) |
| 4 | - Work with **AWS CodeDeploy** for deployment automation.<br>- **Practice:**<br>&emsp;+ Create an EC2 deployment group.<br>&emsp;+ Deploy application revisions using AppSpec.<br>&emsp;+ Test in-place and blue/green deployments.<br><br>→ Learn automated deployment to EC2. | 05/11/2025 | 05/11/2025 | [AWS Study Group](https://000044.awsstudygroup.com/) |
| 5 | - Integrate **Lambda deployments** into CodePipeline.<br>- **Practice:**<br>&emsp;+ Deploy Lambda functions using CodeDeploy Lambda.<br>&emsp;+ Test linear and canary deployment strategies.<br><br>→ Implement CI/CD for serverless workloads. | 06/11/2025 | 06/11/2025 | [AWS Study Group](https://000045.awsstudygroup.com/) |
| 6 | - Add pipeline security and monitoring.<br>- **Practice:**<br>&emsp;+ Enable CloudWatch and SNS notifications.<br>&emsp;+ Configure IAM permissions for pipeline stages.<br>&emsp;+ Add test/approval stages for safer deployments.<br><br>→ Improve CI/CD reliability and governance. | 07/11/2025 | 07/11/2025 | [AWS Study Group](https://000046.awsstudygroup.com/) |

---

### Week 9 Achievements

#### 1. CI/CD Pipeline Fundamentals
- Understood the CI/CD workflow: source → build → test → deploy.  
- Built the first automated **CodePipeline** integrated with GitHub.  

#### 2. Build Automation (CodeBuild)
- Wrote a complete **buildspec.yml** for automated build and testing.  
- Successfully executed builds in an isolated CodeBuild environment.  

#### 3. Deployment Automation (CodeDeploy)
- Configured EC2 deployment groups and executed in-place & blue/green deployments.  
- Understood the role of **AppSpec** and lifecycle hooks.  

#### 4. Serverless Deployment
- Automated deployment of **Lambda functions** using CodeDeploy.  
- Tested safe rollout strategies like **Linear** & **Canary** deployments.  

#### 5. Pipeline Security & Governance
- Added approval steps, IAM permissions, and fine-grained access controls.  
- Monitored pipeline executions using CloudWatch & SNS alerts.  
- Improved reliability and safety of the entire CI/CD workflow.