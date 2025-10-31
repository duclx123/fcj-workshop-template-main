---
title: "Worklog Tuần 8"
date: 2025-10-27
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục tiêu tuần 8:

* Tìm hiểu các khái niệm nâng cao về mạng trên AWS, bao gồm **VPC Peering**, **Transit Gateway**, và **PrivateLink**.  
* Triển khai **kết nối hybrid cloud** giữa on-premises và AWS.  
* Hiểu và cấu hình **AWS Direct Connect** cho kết nối mạng riêng.  
* Thực hành các **best practice bảo mật mạng** và quản lý luồng traffic.  
* Giám sát và xử lý sự cố mạng bằng **VPC Flow Logs** và **CloudWatch**.  

---

### Các công việc cần triển khai trong tuần này:

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|-----|------|-------------|------------------|--------------------|
| 2 | - Tìm hiểu **VPC Peering** và **Transit Gateway**.<br>- **Thực hành:**<br>&emsp;+ Tạo kết nối VPC peering giữa hai VPC.<br>&emsp;+ Cấu hình routing table để điều hướng traffic.<br>&emsp;+ Kiểm tra kết nối giữa các EC2 instance.<br><br>→ Hiểu cách giao tiếp giữa các VPC. | 27/10/2025 | 27/10/2025 | [AWS Study Group](https://000041.awsstudygroup.com/) |
| 3 | - Tìm hiểu **AWS PrivateLink** và endpoint services.<br>- **Thực hành:**<br>&emsp;+ Tạo PrivateLink endpoint để truy cập dịch vụ riêng tư.<br>&emsp;+ Kiểm tra truy cập dịch vụ mà không qua Internet công cộng.<br><br>→ Đảm bảo kết nối riêng tư và bảo mật. | 28/10/2025 | 28/10/2025 | [AWS Study Group](https://000042.awsstudygroup.com/) |
| 4 | - Tìm hiểu **AWS Direct Connect** cho kết nối mạng riêng.<br>- **Thực hành:**<br>&emsp;+ Tạo kết nối Direct Connect.<br>&emsp;+ Thiết lập virtual interface và kiểm tra routing.<br><br>→ Giảm độ trễ và tăng băng thông đáng tin cậy. | 29/10/2025 | 29/10/2025 | [AWS Study Group](https://000043.awsstudygroup.com/) |
| 5 | - Tìm hiểu thiết kế hybrid cloud và tích hợp với on-premises.<br>- **Thực hành:**<br>&emsp;+ Kết nối mạng on-premises với AWS qua VPN và Direct Connect.<br>&emsp;+ Kiểm tra failover và routing giữa cloud và tài nguyên local.<br><br>→ Thực hành kịch bản mạng hybrid. | 30/10/2025 | 30/10/2025 | [AWS Study Group](https://000044.awsstudygroup.com/) |
| 6 | - Thực hành giám sát và bảo mật mạng.<br>- **Thực hành:**<br>&emsp;+ Bật **VPC Flow Logs** và phân tích traffic.<br>&emsp;+ Thiết lập **CloudWatch Alarms** cho sự cố mạng.<br>&emsp;+ Áp dụng **Security Group** và **NACL** theo best practice.<br><br>→ Đảm bảo mạng an toàn và dễ giám sát. | 31/10/2025 | 31/10/2025 | [AWS Study Group](https://000045.awsstudygroup.com/) |

---

### Kết quả tuần 8

#### 1. VPC Peering & Transit Gateway
- Thiết lập thành công **kết nối VPC peering** và kiểm tra giao tiếp giữa các VPC.  
- Cấu hình **Transit Gateway** để tập trung routing cho nhiều VPC.  

#### 2. AWS PrivateLink
- Tạo **PrivateLink endpoints** để truy cập dịch vụ AWS một cách riêng tư.  
- Xác nhận traffic không đi qua Internet công cộng, nâng cao bảo mật.  

#### 3. AWS Direct Connect
- Cấu hình **kết nối mạng riêng** bằng Direct Connect.  
- Kiểm tra routing và cải thiện băng thông cho kết nối hybrid.  

#### 4. Hybrid Cloud Integration
- Kết nối mạng on-premises với AWS qua **VPN + Direct Connect**.  
- Kiểm tra failover, routing, và độ tin cậy của môi trường hybrid.  

#### 5. Network Monitoring & Security
- Bật **VPC Flow Logs** và phân tích traffic.  
- Thiết lập **CloudWatch Alarms** để giám sát sự cố mạng.  
- Áp dụng **Security Groups** và **NACLs** để đảm bảo an toàn.