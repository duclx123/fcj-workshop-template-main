---
title: "Worklog Tuần 9"
date: 2025-11-03
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Mục tiêu tuần 9:

* Học cách thiết kế pipeline **CI/CD** an toàn và có khả năng mở rộng.  
* Xây dựng quy trình triển khai bằng **AWS CodePipeline**, **CodeBuild**, và **CodeDeploy**.  
* Tích hợp GitHub hoặc CodeCommit làm nguồn mã nguồn (source provider).  
* Tự động triển khai ứng dụng lên EC2 và Lambda.  
* Tăng cường bảo mật pipeline và bổ sung các bước kiểm thử tự động.  

---

### Nhiệm vụ thực hiện trong tuần:

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
|------|-----------|---------------|------------------|--------------------|
| 2 | - Tìm hiểu khái niệm **CI/CD pipeline** trên AWS.<br>- Hiểu cách CodePipeline điều phối build → test → deploy.<br>- **Thực hành:**<br>&emsp;+ Tạo CodePipeline cơ bản với GitHub làm nguồn.<br><br>→ Nắm nền tảng về tự động hóa CI/CD. | 03/11/2025 | 03/11/2025 | [AWS Study Group](https://000042.awsstudygroup.com/) |
| 3 | - Tìm hiểu **AWS CodeBuild** để build và test ứng dụng.<br>- **Thực hành:**<br>&emsp;+ Viết file `buildspec.yml`.<br>&emsp;+ Chạy build tự động và test đơn vị.<br><br>→ Hiểu cách tự động hóa build và cấu hình môi trường. | 04/11/2025 | 04/11/2025 | [AWS Study Group](https://000043.awsstudygroup.com/) |
| 4 | - Làm việc với **AWS CodeDeploy** để tự động triển khai ứng dụng.<br>- **Thực hành:**<br>&emsp;+ Tạo deployment group cho EC2.<br>&emsp;+ Triển khai bằng AppSpec.<br>&emsp;+ Kiểm thử triển khai kiểu in-place và blue/green.<br><br>→ Thành thạo triển khai tự động lên EC2. | 05/11/2025 | 05/11/2025 | [AWS Study Group](https://000044.awsstudygroup.com/) |
| 5 | - Tích hợp triển khai **Lambda** vào CodePipeline.<br>- **Thực hành:**<br>&emsp;+ Deploy Lambda qua CodeDeploy.<br>&emsp;+ Test chiến lược triển khai tuyến tính và canary.<br><br>→ Xây dựng CI/CD cho môi trường serverless. | 06/11/2025 | 06/11/2025 | [AWS Study Group](https://000045.awsstudygroup.com/) |
| 6 | - Bổ sung bảo mật và giám sát pipeline.<br>- **Thực hành:**<br>&emsp;+ Bật thông báo CloudWatch + SNS.<br>&emsp;+ Cấu hình IAM cho từng stage của pipeline.<br>&emsp;+ Thêm bước test/approval để triển khai an toàn.<br><br>→ Tăng độ tin cậy và khả năng kiểm soát của pipeline. | 07/11/2025 | 07/11/2025 | [AWS Study Group](https://000046.awsstudygroup.com/) |

---

### Kết quả đạt được trong tuần 9

#### 1. Nền tảng CI/CD
- Hiểu quy trình CI/CD từ source → build → test → deploy.  
- Tạo và vận hành thành công CodePipeline tích hợp GitHub.  

#### 2. Tự động hóa build (CodeBuild)
- Viết và sử dụng file **buildspec.yml** để build & test tự động.  
- Chạy build trong môi trường CodeBuild tách biệt và tối ưu.  

#### 3. Tự động triển khai (CodeDeploy)
- Cấu hình deployment group cho EC2 và thực hành triển khai in-place, blue/green.  
- Hiểu vai trò AppSpec và lifecycle hooks.  

#### 4. Triển khai Serverless
- Tự động triển khai Lambda bằng CodeDeploy.  
- Thành thạo chiến lược rollout an toàn như **Linear** và **Canary**.  

#### 5. Bảo mật & giám sát Pipeline
- Thêm approval steps và phân quyền IAM chi tiết theo stage.  
- Giám sát pipeline bằng CloudWatch và SNS notifications.  
- Tăng cường độ ổn định và an toàn cho toàn bộ quy trình CI/CD.