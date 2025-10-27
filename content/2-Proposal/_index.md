---
title: "Proposal"
date: 2025-01-01
weight: 2
chapter: false
pre: " <b> 2. </b> "
---
{{% notice warning %}}
⚠️ **Note:** The information below is for reference purposes only. Please **do not copy verbatim** for your report, including this warning.
{{% /notice %}}

# Mini Food Social  
## A Serverless Social Platform with AI-Powered Recipe Generation

### 1. Executive Summary
**Mini Food Social** is a lightweight, serverless social web application built for food enthusiasts.  
It allows users to share, discover, and generate new recipes through AI.  
The platform supports up to **50 registered users**, featuring authentication, post creation, image upload, and AI-generated recipe suggestions.  

The system uses a **fully serverless AWS architecture**:
- **AWS Amplify** (Next.js frontend hosting & CI/CD)
- **Amazon API Gateway** + **AWS Lambda** (backend APIs)
- **Amazon DynamoDB** (NoSQL data store)
- **Amazon Bedrock** (AI text generation)
- **Amazon Cognito** (user authentication)
- **Amazon CloudFront + WAF + ACM + Route 53** (secure edge delivery)

The solution is scalable, cost-efficient, and production-ready while remaining affordable for small-scale deployments.

---

### 2. Problem Statement
#### What’s the Problem?
Existing recipe-sharing platforms are static and lack personalization.  
Users want:
- Community-driven interaction (likes, comments, sharing)
- AI-assisted recipe ideas based on ingredients or mood  
- Simple but secure authentication  

However, building a scalable platform with these capabilities often requires complex backend management and expensive compute resources.

#### The Solution
**Mini Food Social** leverages AWS Serverless to eliminate backend management overhead.  
Using an event-driven, pay-per-use model:
- **Amplify** hosts the web UI and handles deployment via GitLab CI/CD.  
- **Cognito** manages sign-in/sign-up and JWT-based authentication.  
- **API Gateway** routes requests to Lambda functions.  
- **Router Lambda** coordinates specialized handlers for posts, user profiles, and AI interactions.  
- **Bedrock** generates recipes dynamically using user prompts.  
- **CloudFront + WAF** protect the app from malicious traffic.  

---

### Benefits and Return on Investment
- **Low-cost scalability** — Pay only per request; ideal for small teams or demo apps.  
- **Modern serverless stack** — No infrastructure maintenance.  
- **AI integration** — Increases engagement and user retention.  
- **Secure & compliant** — Managed auth (Cognito) and encrypted data (S3, DynamoDB).  

**Estimated Monthly Cost (No Free Tier): ≈ $32.60 USD**  
**Annual Cost: ≈ $391.20 USD**  

---

### 3. Solution Architecture
The platform adopts a five-layer serverless architecture built entirely on AWS to ensure scalability, maintainability, and cost efficiency.

At the CI/CD Layer, GitLab automates both frontend and backend deployments — pushing frontend updates to AWS Amplify and provisioning backend infrastructure via AWS CDK and AWS CloudFormation.

The Edge Layer secures all inbound traffic through Amazon Route 53 for domain management, AWS Certificate Manager (ACM) for SSL encryption, AWS WAF for web application firewall protection, and Amazon CloudFront for global content delivery. CloudFront communicates privately with S3 using an Origin Access Identity (OAI) to ensure secure asset access.

Within the Application Layer, AWS Amplify hosts the Next.js frontend, while Amazon API Gateway and AWS Lambda manage backend API requests. Amazon Cognito provides authentication, authorization, and JWT token validation for all user interactions.

The Data Storage Layer leverages Amazon DynamoDB for the main application data, Amazon S3 for storing media and images, and Amazon EventBridge for asynchronous communication and scheduled workflows.

Lastly, the Observability Layer integrates Amazon CloudWatch for logging and monitoring, AWS X-Ray for request tracing and performance visualization, and Amazon SNS for real-time alerting and notifications — ensuring transparency, reliability, and operational efficiency across the platform.

![Mini Food Social Architecture](/images/2-Proposal/FsocialArchitecture.png)

### AWS Services Used
| Category | Services |
|-----------|-----------|
| **Frontend & CI/CD** | AWS Amplify (Next.js), GitLab, AWS CDK, CloudFormation |
| **Edge & Security** | Route 53, ACM, CloudFront, WAF |
| **Application & Compute** | API Gateway, AWS Lambda, Amazon Cognito |
| **Data & AI** | DynamoDB (single-table), S3, Amazon Bedrock |
| **Observability & Events** | CloudWatch, X-Ray, SNS, EventBridge |

---

### Component Design
- **User Access:** User → CloudFront → Amplify (Frontend)
- **Authentication:** CloudFront → Cognito (Hosted UI redirect)
- **API Calls:** Amplify → Route 53 → CloudFront → WAF → API Gateway
- **API Authorization:** API Gateway → Cognito Authorizer
- **Backend Logic:** API Router Lambda → DynamoDB / S3 / Bedrock
- **AI Recipes:** AI Handler Lambda → Bedrock (Claude model)
- **Image Delivery:** CloudFront → S3 (via OAI)
- **Events & Logs:** EventBridge, CloudWatch, X-Ray, SNS

---

### 4. Technical Implementation
#### Implementation Phases
| Phase | Duration | Description |
|--------|-----------|-------------|
| **1. Setup & CI/CD** | Weeks 1–3 | Define architecture, CDK setup, connect Amplify & GitLab |
| **2. Core Backend** | Weeks 4–7 | Build Cognito auth, API Gateway, and Router Lambda |
| **3. Frontend Integration** | Weeks 8–10 | Implement Next.js UI, connect APIs, enable CRUD |
| **4. AI & Monitoring** | Weeks 11–13 | Integrate Bedrock, add CloudWatch and X-Ray |
| **5. Final Testing** | Week 14 | Load test, deploy to production |

#### Technical Requirements
- **Frontend:** Next.js (Amplify hosting)  
- **Backend:** Lambda (Node.js), API Gateway, Cognito (JWT Auth)  
- **AI:** Amazon Bedrock (Claude via SDK)  
- **Database:** DynamoDB single-table with GSI  
- **DevOps:** GitLab CI/CD pipelines for Amplify & CDK  

---

### 5. Timeline & Milestones
| Month | Deliverables |
|--------|--------------|
| **Month 1** | Architecture design, CI/CD pipeline complete |
| **Month 2** | Auth + Backend APIs operational |
| **Month 3** | Frontend integrated, AI & monitoring enabled |
| **End of Month 3** | 🎉 Production-ready deployment |

---

### 6. Budget Estimation
### Infrastructure Costs
The estimated cost for 50 active users per month is calculated based on actual AWS service usage, excluding any Free Tier benefits.

#### AWS Services:
| Service | Description | Estimated Monthly Cost (USD) |
|----------|--------------|-------------------------------|
| **AWS Amplify** | Hosts the Next.js frontend web app | **$1.00** |
| **Amazon CloudFront** | Global CDN distribution for frontend | **$0.50** |
| **AWS WAF** | 1 Web ACL with 1 rule for CloudFront | **$5.00** |
| **Amazon API Gateway** | Handles ~10,000 API requests/month | **$0.15** |
| **AWS Lambda** | 2 functions (API router + Auth handler) | **$0.10** |
| **Amazon DynamoDB** | On-demand mode for small workloads | **$0.25** |
| **Amazon S3** | Stores static assets and backups (2 buckets) | **$0.20** |
| **Amazon Cognito** | Authentication for 50 MAU | **$0.25** |
| **Amazon Bedrock** | Text generation for AI feature (~20K tokens) | **$2.00** |
| **Amazon EventBridge** | Asynchronous event processing | **$0.05** |
| **Amazon Route 53** | Domain registration + hosted zone + DNS queries | **$1.51** |
| **AWS Certificate Manager (ACM)** | SSL certificate for HTTPS | **$0.00** |
| **AWS CloudFormation / CDK Stack** | Infrastructure deployment | **$0.00** |

**➡ Total Estimated Monthly Cost:** ≈ **$11.01 USD**  
**➡ Annual Cost:** ≈ **$132.12 USD**

---

### Hardware & Miscellaneous
- **Development Tools:** Covered by existing local environments (VSCode, GitLab CI/CD, etc.)  
- **Hardware:** None required (serverless architecture)

---

### 7. Risk Assessment
| Risk | Impact | Probability |
|-------|---------|-------------|
| Bedrock cost spikes | Medium | Low |
| Auth misconfig (Cognito) | High | Medium |
| WAF rule misconfig | Medium | Low |

**Mitigation:**  
- Limit Bedrock token count & monitor via CloudWatch alarms.  
- Use least-privilege IAM roles.  
- Test WAF ACLs before production.

---

### 8. Expected Outcomes
#### Technical Improvements
- Fully functional **serverless web social app** with AI recipe generation.  
- Secure and scalable backend with **Cognito + WAF**.  
- Observable and maintainable architecture with **CloudWatch & X-Ray**.  

#### Long-term Value
- Demonstrates applied knowledge in **Serverless, DevOps, and AI Integration**.  
- Scalable to 500+ users with minor configuration changes.  
- Reusable as a reference template for future AWS projects.
