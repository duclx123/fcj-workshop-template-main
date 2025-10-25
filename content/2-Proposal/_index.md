---
title: "Proposal"
date: 2025-01-01
weight: 2
chapter: false
pre: " <b> 2. </b> "
---
⚠️ Note: The information below is a draft based on our conversations. Please do not copy verbatim for your report. You must adapt and refine it with your team's specific goals and data, including this warning.

Mini Food Social: An AI-Powered Serverless Recipe Platform
A Unified AWS Serverless Solution for Social Food Discovery and AI-Driven Recipe Generation
1. Executive Summary
The Mini Food Social platform is an advanced, serverless social media application designed for food enthusiasts. It provides a community-driven space for users to share, discover, and save recipes, differentiating itself through integrated AI-powered recipe suggestions. The platform is built entirely on a production-grade AWS Serverless stack, featuring AWS Amplify for the frontend, AWS Lambda with Amazon API Gateway for the backend, DynamoDB for a scalable single-table database, and Amazon Bedrock for generative AI capabilities. The architecture is secured from the edge with CloudFront and AWS WAF, with robust user management handled by Amazon Cognito, ensuring a scalable, secure, and cost-efficient solution.

2. Problem Statement
What’s the Problem?
Existing recipe platforms are often static repositories or closed social networks. They lack deep personalization and fail to inspire creativity. Users struggle to find new recipes tailored to their specific tastes or available ingredients, and managing their own creations alongside community content is often clunky. There is a gap in the market for a platform that seamlessly blends social sharing with powerful, generative AI for true recipe discovery.

The Solution
The Mini Food Social platform addresses this by leveraging a modern, event-driven AWS architecture:

Frontend & Hosting: A Next.js application hosted on AWS Amplify provides a fast, responsive user interface.

API & Security: All API requests are routed through Amazon CloudFront and AWS WAF for edge security and caching. API Gateway acts as the front door, using a Cognito Authorizer to validate every user request.

Backend Logic: API Gateway forwards requests to a central API Router Lambda, which follows the "single entry point" pattern. This router dispatches tasks to a suite of specialized micro-functions (e.g., posts-handler, user-profile-handler, ai-suggestion-handler).

AI Integration: The ai-suggestion-handler Lambda interfaces directly with Amazon Bedrock to provide users with unique, AI-generated recipe ideas.

Data & Storage: All application data (users, posts, recipes) is stored in a highly scalable DynamoDB single-table database. User-uploaded images are stored securely in Amazon S3 (set to private) and served globally via CloudFront + OAI.

Authentication: Amazon Cognito handles the entire user lifecycle (sign-up, sign-in, token management), including custom sign-up logic via Cognito Triggers (using the Auth-Handler Lambda).

Benefits and Return on Investment
This solution provides a highly personalized and engaging social experience for users. For the development team, it serves as a powerful, production-ready portfolio piece demonstrating mastery of modern serverless architecture, CI/CD (via GitLab and CDK), and AI integration. The pay-per-use serverless model ensures extremely low operational costs, with the AWS Free Tier likely covering most initial usage. The architecture is designed for massive scalability, capable of handling thousands of users with zero manual infrastructure management.

3. Solution Architecture
The platform utilizes a 100% serverless, event-driven architecture. The entire infrastructure is defined as code (IaC) using the AWS CDK and deployed automatically via a GitLab CI/CD pipeline.

The architecture is logically divided into layers:

CI/CD Layer: Developers push code to GitLab, which triggers separate pipelines for the Amplify Frontend and the CDK Backend (CloudFormation).

Edge Layer: Users (and the frontend app) access all resources via Route 53 and CloudFront. AWS WAF blocks malicious traffic, and ACM provides SSL.

Application Layer: API Gateway validates tokens with Cognito and routes requests to the API Router Lambda. This core Lambda orchestrates calls to other Lambdas, Bedrock, and the Data Layer.

Data Storage Layer: DynamoDB (single-table) serves as the primary database, while S3 stores image assets.

Observability Layer: The entire system is monitored via CloudWatch (Metrics & Logs), X-Ray (Traces), and alerts are pushed via SNS. EventBridge is used to trigger scheduled jobs.

(Here you should insert the final "mạng nhện" diagram you created. The description below is based on it.)

[PLACEHOLDER FOR YOUR ARCHITECTURE DIAGRAM (image_354c01.png)]

AWS Services Used
Frontend & CI/CD: AWS Amplify (Next.js), AWS CDK, AWS CloudFormation.

Edge & Security: Amazon Route 53, Amazon CloudFront, AWS WAF, AWS Certificate Manager (ACM).

Application & Compute: Amazon API Gateway, AWS Lambda (11+ functions, incl. API Router, Auth Handler), Amazon Cognito.

Data & AI: Amazon DynamoDB (Single-Table Design), Amazon S3, Amazon Bedrock.

Observability & Events: Amazon CloudWatch, AWS X-Ray, Amazon SNS (Alerts), Amazon EventBridge.

Component Design
User Access: Users access the frontend app via Flow 10: User -> Amplify.

Authentication: The Amplify app uses Flow 15: Amplify <-> Cognito to sign in users and get a JWT token.

API Calls: The frontend (Amplify) calls the backend API using Flow 5-9: Amplify -> Route 53 -> ... -> WAF.

API Security: Flow 16: API Gateway -> Cognito (Cognito Authorizer) validates the token before executing any logic.

Backend Logic: Flow 12: API Gateway -> API Router Lambdas. The router then calls other services like (13) DynamoDB, (19) S3, and (14) Bedrock.

Image Delivery: User images are served securely using Flow 18: CloudFront -> S3 (with OAI).

Monitoring: All key components (API Gateway, Lambdas, DynamoDB) send data to CloudWatch and X-Ray (Flows 21, 24, 25, 26, etc.).

4. Technical Implementation
Implementation Phases

Phase 1: Architecture & CI/CD (Weeks 1-3): Finalize PROD architecture design, define the DynamoDB single-table data model, and establish the GitLab CI/CD pipeline using AWS CDK for automated backend deployment.

Phase 2: Core Backend (Weeks 4-7): Implement core infrastructure: API Gateway, Cognito (Authorizer & Triggers), API Router Lambda, and DynamoDB tables/GSIs.

Phase 3: Frontend & Feature Integration (Weeks 8-10): Develop the Next.js frontend on Amplify. Implement core CRUD (Create, Read, Update, Delete) features for user profiles and posts.

Phase 4: AI & Observability (Weeks 11-13): Integrate Amazon Bedrock for the AI suggestion feature. Finalize the full Observability stack (CloudWatch Dashboards, X-Ray Tracing, SNS Alerts).

Phase 5: Testing & Go-Live (Week 14): End-to-end testing, load testing, security hardening (WAF rules), and final deployment to production.

Technical Requirements

Backend: AWS CDK (TypeScript) for Infrastructure as Code (IaC).

Compute: AWS Lambda (Node.js) using the "Router" pattern for efficient microservice orchestration.

Database: Deep understanding of DynamoDB single-table design and GSI query patterns.

Frontend: Next.js framework hosted on AWS Amplify.

AI: Proficiency with the AWS SDK for Amazon Bedrock (e.g., calling Anthropic Claude).

DevOps: GitLab CI/CD pipeline configuration for automated builds, tests, and deployments to dev and prod environments.

5. Timeline & Milestones
Month 1: Project Kick-off. Finalize architecture (diagram) and data models. CI/CD pipeline established. Core backend (API Gateway, Lambda, Cognito, DynamoDB) deployed.

Month 2: User authentication (sign-up, sign-in) is fully functional. Frontend connected to the backend. Users can create, read, and update profiles and recipe posts.

Month 3: AI (Bedrock) feature implemented. Observability stack (CloudWatch, X-Ray) is configured with alerts. Final testing and documentation.

Project Launch (End of Month 3): Platform deployed and live on the production domain.

6. Budget Estimation
The serverless architecture is extremely cost-effective. Most services fall within the AWS Free Tier for initial usage.

(Please replace this section with your own AWS Pricing Calculator link and refined numbers.)

You can find a preliminary budget estimation on the . Or you can download the .

Infrastructure Costs (Monthly Estimate, Post-Free Tier)

AWS Lambda: $0.00 (1M requests/mo in Free Tier).

API Gateway: $0.00 (1M requests/mo in Free Tier).

DynamoDB: $0.00 (25 GB Storage, 25 WCU/RCU in Free Tier).

Amazon S3: ~$0.23/month (Estimate for 10GB Standard storage).

AWS Amplify (Hosting): ~$1.00/month (Low traffic hosting).

CloudFront & Data Transfer: ~$0.50/month.

AWS WAF: ~$1.00/month (Base cost for rules).

Amazon Bedrock: (Variable) This is the primary scaling cost, dependent on model choice and tokens processed.

Observability (CloudWatch, X-Ray, SNS): $0.00 (Covered by generous Free Tier).

Amazon Cognito: $0.00 (Up to 50,000 MAUs in Free Tier).

Total: ~ $2.73/month (plus variable Amazon Bedrock costs).

7. Risk Assessment
Risk Matrix
Cost Overrun (Bedrock): High Impact, Medium Probability. Generative AI calls can become expensive if not rate-limited or monitored.

Security Vulnerability (IAM/WAF): High Impact, Low Probability. A misconfigured IAM role or WAF rule could expose data.

Scalability Bottleneck (DynamoDB): Medium Impact, Low Probability. A poor GSI design could lead to "hot partitions" or slow queries at scale.

Mitigation Strategies
Cost: Implement AWS Budget Alerts (using the CostAlertTopic SNS topic already in the design). Implement rate limiting at the API Gateway level for the Bedrock-powered endpoint.

Security: Use AWS CDK (IaC) to enforce least-privilege IAM roles. Rely on AWS WAF for L7 protection and the Cognito Authorizer to secure every API endpoint by default.

Scalability: Conduct thorough data modeling and load testing against the DynamoDB single-table design to validate query patterns before launch.

8. Expected Outcomes
Technical Improvements
A fully-functional, production-grade serverless application. It demonstrates a modern, secure, and highly scalable architecture. The system provides robust monitoring and alerting out-of-the-box via the Observability Layer.

Long-term Value
This platform serves as a powerful portfolio project for the team, demonstrating cutting-edge skills in Serverless, DevOps (IaC), and Generative AI. It creates a scalable foundation that can grow to thousands of users with minimal operational cost and management overhead, and can be extended with more advanced AI-driven features in the future.