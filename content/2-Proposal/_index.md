---
title: "Proposal"
date: 2025-01-01
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# Mini Food Social: An AI-Powered Serverless Recipe Platform  
### A Unified AWS Serverless Solution for Social Food Discovery and AI-Driven Recipe Generation

---

## 1. Executive Summary

The **Mini Food Social** platform is an advanced, serverless social media application designed for food enthusiasts. It provides a community-driven space for users to share, discover, and save recipes, differentiating itself through integrated AI-powered recipe suggestions.

The platform is built entirely on a **production-grade AWS Serverless stack**, featuring:

- **AWS Amplify** for the frontend  
- **AWS Lambda** with **Amazon API Gateway** for the backend  
- **DynamoDB** for a scalable single-table database  
- **Amazon Bedrock** for generative AI capabilities  

The architecture is secured from the edge with **CloudFront** and **AWS WAF**, with robust user management handled by **Amazon Cognito**, ensuring a scalable, secure, and cost-efficient solution.

---

## 2. Problem Statement

### What’s the Problem?

Existing recipe platforms are often static repositories or closed social networks.  
They lack deep personalization and fail to inspire creativity.  
Users struggle to find new recipes tailored to their specific tastes or available ingredients, and managing their own creations alongside community content is often clunky.

👉 **There is a gap** in the market for a platform that seamlessly blends social sharing with powerful, generative AI for true recipe discovery.

---

### The Solution

The **Mini Food Social** platform addresses this by leveraging a modern, event-driven AWS architecture:

- **Frontend & Hosting:** Next.js app hosted on **AWS Amplify** for a fast, responsive UI.  
- **API & Security:** All requests routed through **CloudFront** + **WAF**, with **API Gateway** using **Cognito Authorizer** for validation.  
- **Backend Logic:** Central **API Router Lambda** dispatches tasks to specialized micro-Lambdas (e.g., posts-handler, user-profile-handler, ai-suggestion-handler).  
- **AI Integration:** `ai-suggestion-handler` interfaces directly with **Amazon Bedrock** for AI-generated recipes.  
- **Data & Storage:** Application data in **DynamoDB (single-table)**; images in **S3**, served securely via CloudFront + OAI.  
- **Authentication:** **Amazon Cognito** manages user lifecycle with custom sign-up triggers via `Auth-Handler Lambda`.

---

### Benefits and Return on Investment

- Highly personalized and engaging user experience.  
- Production-ready **portfolio project** demonstrating mastery of modern AWS serverless architecture, CI/CD, and AI.  
- **Pay-per-use** model ensures extremely low operational costs (mostly covered by AWS Free Tier).  
- Designed for **massive scalability** with zero manual infrastructure management.

---

## 3. Solution Architecture

The platform utilizes a **100% serverless, event-driven architecture**.  
Infrastructure is defined as code (IaC) using **AWS CDK** and deployed automatically via **GitLab CI/CD**.

---

### Architecture Layers

1. **CI/CD Layer:**  
   Code pushed to GitLab triggers pipelines for Amplify (Frontend) and CDK (Backend via CloudFormation).

2. **Edge Layer:**  
   Access through **Route 53**, **CloudFront**, and **WAF**. **ACM** provides SSL.

3. **Application Layer:**  
   **API Gateway** validates tokens with **Cognito**, routes requests to **API Router Lambda**, which calls other Lambdas, **Bedrock**, and the Data Layer.

4. **Data Storage Layer:**  
   **DynamoDB** (single-table) for data, **S3** for images.

5. **Observability Layer:**  
   **CloudWatch**, **X-Ray**, and **SNS** for logs, metrics, and alerts.  
   **EventBridge** triggers scheduled jobs.

---

### Architecture Diagram

> (Insert your final “mạng nhện” diagram here.)  
>  
> **[PLACEHOLDER FOR YOUR ARCHITECTURE DIAGRAM (image_354c01.png)]**

---

### AWS Services Used

| Category | Services |
|-----------|-----------|
| **Frontend & CI/CD** | AWS Amplify (Next.js), AWS CDK, AWS CloudFormation |
| **Edge & Security** | Amazon Route 53, Amazon CloudFront, AWS WAF, ACM |
| **Application & Compute** | API Gateway, AWS Lambda, Amazon Cognito |
| **Data & AI** | DynamoDB (Single-Table), S3, Amazon Bedrock |
| **Observability & Events** | CloudWatch, X-Ray, SNS, EventBridge |

---

### Component Design

- **User Access:** Flow 10 → User → Amplify  
- **Authentication:** Flow 15 → Amplify ↔ Cognito (JWT token)  
- **API Calls:** Flows 5–9 → Amplify → Route 53 → WAF → API Gateway  
- **API Security:** Flow 16 → API Gateway → Cognito (Authorizer validation)  
- **Backend Logic:** Flow 12 → API Gateway → API Router Lambdas → DynamoDB / S3 / Bedrock  
- **Image Delivery:** Flow 18 → CloudFront → S3 (OAI)  
- **Monitoring:** Flows 21, 24–26 → CloudWatch & X-Ray

---

## 4. Technical Implementation

### Implementation Phases

| Phase | Duration | Description |
|-------|-----------|-------------|
| **1. Architecture & CI/CD** | Weeks 1–3 | Finalize architecture, define DynamoDB single-table model, establish GitLab CI/CD using CDK |
| **2. Core Backend** | Weeks 4–7 | Implement API Gateway, Cognito, Router Lambda, DynamoDB |
| **3. Frontend & Integration** | Weeks 8–10 | Develop Next.js on Amplify, implement CRUD for profiles & posts |
| **4. AI & Observability** | Weeks 11–13 | Integrate Bedrock, configure CloudWatch, X-Ray, SNS |
| **5. Testing & Go-Live** | Week 14 | End-to-end testing, load/security testing, deploy to production |

---

### Technical Requirements

- **Backend:** AWS CDK (TypeScript)  
- **Compute:** AWS Lambda (Node.js, Router pattern)  
- **Database:** DynamoDB single-table design + GSI  
- **Frontend:** Next.js on AWS Amplify  
- **AI:** AWS SDK with Amazon Bedrock (Anthropic Claude)  
- **DevOps:** GitLab CI/CD for automated deploys

---

## 5. Timeline & Milestones

| Month | Key Deliverables |
|--------|------------------|
| **Month 1** | Architecture & data model finalized, CI/CD pipeline ready, Core backend deployed |
| **Month 2** | User auth complete, frontend integrated, basic CRUD features live |
| **Month 3** | AI (Bedrock) integrated, Observability stack live, final testing & documentation |
| **End of Month 3** | 🚀 **Platform Launch** (Production domain) |

---

## 6. Budget Estimation

The **serverless architecture** is highly cost-effective.  
Most services are **within AWS Free Tier** for early usage.

> (Replace with your AWS Pricing Calculator link & refined numbers.)

| Service | Monthly Cost (Post-Free Tier) |
|----------|-------------------------------|
| AWS Lambda | $0.00 (1M requests/mo free) |
| API Gateway | $0.00 (1M requests/mo free) |
| DynamoDB | $0.00 (25GB, 25WCU/RCU free) |
| S3 | ~$0.23 (10GB) |
| Amplify | ~$1.00 (low traffic) |
| CloudFront | ~$0.50 |
| WAF | ~$1.00 |
| Bedrock | Variable (depends on tokens) |
| CloudWatch, X-Ray, SNS | $0.00 (Free Tier) |
| Cognito | $0.00 (≤50,000 MAUs) |

**Estimated Total:** ~$2.73/month (excluding Bedrock)

---

## 7. Risk Assessment

### Risk Matrix

| Risk | Impact | Probability |
|-------|---------|-------------|
| **Cost Overrun (Bedrock)** | High | Medium |
| **Security Vulnerability (IAM/WAF)** | High | Low |
| **Scalability Bottleneck (DynamoDB)** | Medium | Low |

---

### Mitigation Strategies

- **Cost:** Use AWS Budget Alerts (SNS). Implement API Gateway rate limiting on Bedrock endpoints.  
- **Security:** Enforce least-privilege IAM roles via CDK. Protect APIs with WAF + Cognito Authorizer.  
- **Scalability:** Test DynamoDB data models and GSI query patterns before launch.

---

## 8. Expected Outcomes

### Technical Improvements
A fully-functional, production-grade serverless application demonstrating:
- Secure, scalable, event-driven AWS architecture  
- Robust observability via CloudWatch, X-Ray, SNS  
- CI/CD automation with GitLab + CDK

### Long-term Value
- Serves as a **portfolio-grade** project showcasing expertise in Serverless, DevOps, and Generative AI.  
- Scales effortlessly to thousands of users with minimal cost.  
- Provides a foundation for future AI-driven extensions and growth.

---
