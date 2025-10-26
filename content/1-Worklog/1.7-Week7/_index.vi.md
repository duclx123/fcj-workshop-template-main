---
title: "Worklog Tuần 7"
date: 2025-10-20
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Mục tiêu Tuần 7:

* Hiểu khái niệm và lợi ích của **containerization (đóng gói ứng dụng)** trong phát triển phần mềm.  
* Học cách xây dựng, quản lý và triển khai **Docker containers**.  
* Tìm hiểu về **Amazon ECS (Elastic Container Service)** và **ECR (Elastic Container Registry)**.  
* Triển khai ứng dụng web dạng container sử dụng **ECS Fargate**.  
* Làm quen với **tự động hóa CI/CD** trong quy trình triển khai container.  

---

### Các công việc cần triển khai trong tuần này:

| Ngày | Nhiệm vụ | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|------|-----------|---------------|------------------|--------------------|
| 2 | - Ôn lại sự khác biệt giữa **Container** và **Máy ảo (Virtual Machine)**.<br>- Tìm hiểu vai trò của Docker trong việc đóng gói và cô lập ứng dụng.<br>- **Thực hành:**<br>&emsp;+ Cài đặt **Docker Desktop**.<br>&emsp;+ Tạo **Dockerfile** cho ứng dụng web đơn giản (Node.js hoặc Python Flask).<br>&emsp;+ Build và chạy container cục bộ.<br><br>→ Hiểu rõ cách hoạt động cơ bản của containerization. | 20/10/2025 | 20/10/2025 | [AWS Study Group](https://000036.awsstudygroup.com/) |
| 3 | - Tìm hiểu về **Amazon Elastic Container Registry (ECR)**.<br>- **Thực hành:**<br>&emsp;+ Tạo repository trong ECR.<br>&emsp;+ Tag và push image Docker lên ECR.<br>&emsp;+ Kiểm tra lưu trữ và phân quyền truy cập image.<br><br>→ Nắm vững cách quản lý image trong AWS. | 21/10/2025 | 21/10/2025 | [AWS Study Group](https://000037.awsstudygroup.com/) |
| 4 | - Khám phá các khái niệm cơ bản của **Amazon Elastic Container Service (ECS)**.<br>- **Thực hành:**<br>&emsp;+ Tạo **ECS Cluster** sử dụng **Fargate**.<br>&emsp;+ Định nghĩa **Task Definition** và **Service**.<br>&emsp;+ Triển khai ứng dụng container lên ECS.<br><br>→ Hiểu quy trình điều phối container trên AWS. | 22/10/2025 | 22/10/2025 | [AWS Study Group](https://000038.awsstudygroup.com/) |
| 5 | - Tích hợp **Load Balancer** vào ECS.<br>- **Thực hành:**<br>&emsp;+ Cấu hình **Application Load Balancer (ALB)**.<br>&emsp;+ Kết nối ECS service với ALB để truy cập công khai.<br>&emsp;+ Kiểm tra khả năng mở rộng và tính sẵn sàng cao.<br><br>→ Đảm bảo tính ổn định và mở rộng cho ứng dụng container. | 23/10/2025 | 23/10/2025 | [AWS Study Group](https://000039.awsstudygroup.com/) |
| 6 | - Tự động hóa quy trình triển khai bằng **AWS CodePipeline** và **CodeBuild**.<br>- **Thực hành:**<br>&emsp;+ Thiết lập pipeline CI/CD để build image Docker.<br>&emsp;+ Tự động triển khai lên ECS khi có cập nhật.<br>&emsp;+ Kiểm tra triển khai không downtime.<br><br>→ Xây dựng quy trình triển khai tự động và liên tục. | 24/10/2025 | 24/10/2025 | [AWS Study Group](https://000040.awsstudygroup.com/) |

---

### Thành tựu đạt được trong Tuần 7

#### 1. Nền tảng Docker
- Hiểu sự khác biệt giữa container và máy ảo, cũng như lý do container nhẹ hơn.  
- Tạo và kiểm thử **Docker container** cục bộ bằng **Dockerfile** tự viết.  

#### 2. Quản lý image với ECR
- Tạo và quản lý **repository ECR** riêng tư.  
- Push và pull thành công image Docker từ **AWS ECR**.  

#### 3. Triển khai bằng ECS
- Xây dựng và triển khai ứng dụng container hóa bằng **ECS Fargate**.  
- Cấu hình **Task Definition**, **Service**, và mạng cho ECS workload.  

#### 4. Cân bằng tải và mở rộng
- Tích hợp **Application Load Balancer (ALB)** để truy cập công khai.  
- Kiểm tra khả năng tự động mở rộng và phân phối tải giữa các container.  

#### 5. Tự động hóa CI/CD
- Thiết lập **pipeline CI/CD** sử dụng **CodePipeline** và **CodeBuild**.  
- Tự động hóa quy trình build image và triển khai lên ECS.  
- Đạt được triển khai ổn định, nhanh chóng và không gián đoạn dịch vụ.