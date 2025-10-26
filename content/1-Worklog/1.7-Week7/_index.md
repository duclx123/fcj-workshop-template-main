---
title: "Week 7 Worklog"
date: 2025-10-20
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Week 7 Objectives:

* Understand the concepts and benefits of **containerization** in application development.  
* Learn how to build, manage, and deploy **Docker containers**.  
* Explore **Amazon ECS (Elastic Container Service)** and **ECR (Elastic Container Registry)**.  
* Deploy a containerized web application using **ECS Fargate**.  
* Introduce **CI/CD automation** for container deployment pipelines.  

---

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
|-----|------|-------------|------------------|--------------------|
| 2 | - Review the difference between **Containers and Virtual Machines**.<br>- Study the role of Docker in application packaging and isolation.<br>- **Practice:**<br>&emsp;+ Install Docker Desktop.<br>&emsp;+ Create a **Dockerfile** for a simple web app (Node.js or Python Flask).<br>&emsp;+ Build and run the container locally.<br><br>→ Gain hands-on understanding of containerization. | 20/10/2025 | 20/10/2025 | [AWS Study Group](https://000036.awsstudygroup.com/) |
| 3 | - Learn about **Amazon Elastic Container Registry (ECR)**.<br>- **Practice:**<br>&emsp;+ Create an ECR repository.<br>&emsp;+ Tag and push the Docker image to ECR.<br>&emsp;+ Verify image storage and permissions.<br><br>→ Understand image management in AWS. | 21/10/2025 | 21/10/2025 | [AWS Study Group](https://000037.awsstudygroup.com/) |
| 4 | - Explore **Amazon Elastic Container Service (ECS)** basics.<br>- **Practice:**<br>&emsp;+ Create an ECS Cluster using **Fargate** launch type.<br>&emsp;+ Define Task Definitions and Services.<br>&emsp;+ Deploy the containerized app.<br><br>→ Learn orchestration of containers in AWS. | 22/10/2025 | 22/10/2025 | [AWS Study Group](https://000038.awsstudygroup.com/) |
| 5 | - Integrate **Load Balancing** with ECS.<br>- **Practice:**<br>&emsp;+ Configure **Application Load Balancer (ALB)**.<br>&emsp;+ Connect ECS service to ALB for public access.<br>&emsp;+ Test high availability and scaling.<br><br>→ Ensure scalability and availability for container apps. | 23/10/2025 | 23/10/2025 | [AWS Study Group](https://000039.awsstudygroup.com/) |
| 6 | - Automate deployments using **AWS CodePipeline** and **CodeBuild**.<br>- **Practice:**<br>&emsp;+ Set up CI/CD pipeline to build Docker images.<br>&emsp;+ Deploy updates automatically to ECS.<br>&emsp;+ Test zero-downtime deployment.<br><br>→ Build automation and continuous delivery workflow. | 24/10/2025 | 24/10/2025 | [AWS Study Group](https://000040.awsstudygroup.com/) |

---

### Week 7 Achievements

#### 1. Docker Fundamentals
- Understood how containers differ from virtual machines and why they are lightweight.  
- Created and tested **Docker containers** locally using custom Dockerfiles.  

#### 2. ECR Image Management
- Created and managed private **ECR repositories**.  
- Successfully pushed and pulled Docker images from AWS ECR.  

#### 3. ECS Deployment
- Built and deployed containerized applications using **ECS Fargate**.  
- Configured task definitions, services, and networking settings for ECS workloads.  

#### 4. Load Balancing and Scaling
- Integrated **Application Load Balancer (ALB)** with ECS services for public access.  
- Verified automatic scaling and traffic distribution between containers.  

#### 5. CI/CD Automation
- Implemented a simple **CI/CD pipeline** using **CodePipeline** and **CodeBuild**.  
- Automated image build and deployment process to ECS.  
- Achieved efficient, repeatable, and zero-downtime container deployments.
