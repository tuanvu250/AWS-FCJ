---
title: "Event 1"
date: "2025-09-09"
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

# Bài thu hoạch “Gen AI & Data”

### Mục Đích Của Sự Kiện

- Cập nhật **xu hướng và chiến lược GenAI** trên AWS  
- Tìm hiểu **xây dựng nền tảng dữ liệu hợp nhất** phục vụ AI/Analytics  
- Giới thiệu **AI-Driven Development Lifecycle (AI-DLC)** trong phát triển phần mềm  
- Học hỏi về **bảo mật cho ứng dụng GenAI** và **AI Agent trong doanh nghiệp**

### Danh Sách Diễn Giả

- **Jun Kai Loke** – AI/ML Specialist SA, AWS  
- **Kien Nguyen** – Solutions Architect, AWS  
- **Tamelly Lim** – Storage Specialist SA, AWS  
- **Binh Tran** – Senior Solutions Architect, AWS  
- **Taiki Dang** – Solutions Architect, AWS  
- **Michael Armentano** – Principal WW GTM Specialist, AWS 

### Nội Dung Nổi Bật

#### 1. Xây dựng Nền tảng Dữ liệu Thống nhất trên AWS cho AI & Analytics
- Chiến lược xây dựng nền tảng dữ liệu hợp nhất, mở rộng, phục vụ AI/Analytics.  
- Luồng dữ liệu end-to-end: ingestion → lưu trữ → xử lý → truy cập → governance.  
- Khắc phục 3 silo (Data/People/Business); self-service + chuẩn hóa quản trị.  
- Dịch vụ trọng tâm: **S3, Glue, Redshift, Lake Formation, OpenSearch, Kinesis/MSK**.

#### 2. Xây dựng Tương lai: Chiến lược Áp dụng GenAI trên AWS
- Tầm nhìn & xu hướng GenAI; lộ trình áp dụng trong doanh nghiệp.  
- **Amazon Bedrock**: chọn model, tùy chỉnh/RAG, guardrails, tối ưu chi phí/độ trễ.  
- **AgentCore**: runtime độc lập framework, gateway tích hợp công cụ, identity/observability.  
- **Amazon Nova** và hệ sinh thái frameworks (**CrewAI, LangGraph, LlamaIndex, Strands**).

#### 3. Bảo mật Ứng dụng Trí tuệ Nhân tạo Sinh tạo với AWS
- Rủi ro theo **OWASP LLM (LLM01/02)**, kiểm soát đầu ra an toàn.  
- Bảo mật theo lớp: **hạ tầng, mô hình, ứng dụng**; IAM, mã hóa, zero-trust, giám sát liên tục.  
- **5 trụ cột bảo mật**: Compliance & Governance, Legal & Privacy, Controls, Risk Management, Resilience.  
- **Generative AI Security Scoping Matrix (Scope 1 → 5)**: từ consumer apps đến self-trained models.  
- **Bedrock Guardrails**: lọc nội dung nhạy cảm với ngưỡng cấu hình.  
- **Human-in-the-loop**: con người phê duyệt/can thiệp khi cần.  
- **Observability (OpenTelemetry)**: giám sát, log, trace minh bạch hành vi AI.


#### 4. Vượt xa Tự động hóa: AI Agents như Công cụ Nhân Năng suất
- Agentic AI: từ assistant → multi-agent systems; giảm giám sát, tăng tự chủ.  
- Ứng dụng: hỗ trợ khách hàng, BI với **Amazon Q (QuickSight)**, tự động hóa quy trình.  
- **Amazon Q in QuickSight**: Build Dashboards/Reports, Data Q&A, Executive Summaries.  
- Giá trị kỳ vọng: **năng suất vượt bậc**; yêu cầu nền tảng dữ liệu & governance vững chắc.

#### 5. Độ Tin cậy và Tính đúng đắn của GenAI
- Vấn đề **hallucination** → giảm thiểu qua: Prompt Engineering, RAG, Fine-tuning, Parameter Tuning.  
- **RAG in action**: user input → embedding → context → LLM → response.  

#### 6. Vòng đời Phát triển Hướng dẫn bởi AI (AI-DLC)
- Vòng đời **AI-centric**: Inception → Construction → Operation.  
- Tiến hóa: **AI-Assisted → AI-Driven → AI-Managed**; AI điều phối, con người phê duyệt.  
- Hạ tầng triển khai: **IaC, test tự động, quan sát và quản trị rủi ro**.

#### 7. Amazon SageMaker (Unified Studio – thế hệ mới)
- **Một môi trường hợp nhất** cho **data, analytics, và AI**: SQL analytics, data processing, model dev/training, **GenAI app dev**, BI, streaming, search analytics.  
- **Lakehouse + Governance**: catalog/lineage, policy-based access, auditing; quản trị **Data & AI** đồng nhất.  
- **Zero-ETL integration**: lõi **S3 ↔ Redshift**, kết nối **Aurora, DynamoDB, RDS, OpenSearch, Kinesis/MSK, Salesforce, SAP, ServiceNow**.  
- **MLOps đầy đủ**: pipelines/experiments, model registry, deployment endpoints, **Feature Store**, monitoring.  
- **Tích hợp Bedrock & JumpStart**: dùng Foundation Models (qua Bedrock), mẫu tham chiếu & tăng tốc triển khai trên SageMaker.


### Những Gì Học Được

#### Tư Duy Thiết K Kế

- **Business-first approach**: Luôn bắt đầu từ nhu cầu kinh doanh thay vì chỉ tập trung vào công nghệ.  
- **Ubiquitous language**: Tầm quan trọng của ngôn ngữ chung giữa business và kỹ thuật, đặc biệt khi trao đổi với mentor/team.  
- **Bounded contexts**: Hiểu cách chia nhỏ domain, tránh phức tạp hóa khi mở rộng hệ thống.

#### Kiến Trúc & Công Nghệ

- **Xây dựng Data Foundation hợp nhất**: Ingestion → Lưu trữ → Xử lý → Truy cập → Governance.  
- **GenAI trên AWS**: Bedrock (model choice, guardrails, RAG), AgentCore (runtime, gateway, identity, observability), Nova LLMs.  
- **AI Agents**: Từ assistant → multi-agent systems; ứng dụng thực tế như customer support, BI với Amazon Q.  
- **AI-DLC**: Vòng đời phát triển có AI làm trung tâm (Inception → Construction → Operation).  
- **Security-first mindset**: Guardrails, human-in-the-loop, tuân thủ & giám sát (OpenTelemetry).

#### Chiến Lược & Ứng Dụng

- **Phased approach**: Không vội vàng, cần roadmap rõ ràng cho hiện đại hóa và áp dụng AI.  
- **Zero-ETL & Unified Studio (SageMaker)**: Giảm phức tạp trong tích hợp dữ liệu, quản lý lifecycle AI tập trung.  
- **ROI measurement**: Không chỉ cost saving mà còn agility, productivity.

---

### Ứng Dụng Vào Công Việc Cá Nhân

- **Trong dự án**:  
  - Có thể thử áp dụng **AI Agent** để hỗ trợ quy trình đăng ký/đăng nhập hoặc customer support.  
  - Sử dụng **validation/guardrails** để tăng tính an toàn khi tích hợp GenAI vào app.  

- **Trong học tập & team project (Sprint 0, serverless vs containerization)**:  
  - Áp dụng kiến thức **AI-DLC** để chia task hợp lý: AI hỗ trợ nghiên cứu/tạo code, team review & approve.  
  - Hiểu khi nào nên dùng **Lambda (serverless)** và khi nào cần **container (ECS/Fargate)**.  

- **Trong vai trò học việc**:  
  - Nhận ra cần **business-first approach** khi viết tài liệu/thu thập yêu cầu.  
  - Thấy rõ **tầm quan trọng của data foundation** để bất kỳ ứng dụng GenAI nào hoạt động đúng và có giá trị.

---

### Trải Nghiệm Trong Event

- Học hỏi trực tiếp từ các chuyên gia AWS về **Data, GenAI adoption, Security, AI Agents, AI-DLC**.  
- Slide và case study giúp mình hình dung rõ **AgentCore** hoạt động thế nào trong thực tế.  
- Thấy được **cách AWS định hình tương lai phát triển phần mềm**: AI không chỉ hỗ trợ mà trở thành một phần của lifecycle.  
- Cảm nhận rõ ràng rằng để ứng dụng GenAI hiệu quả, phải có **nền tảng dữ liệu tốt + bảo mật nghiêm ngặt + chiến lược áp dụng bài bản**.

---

### Bài Học Rút Ra

- **AI Agents** và **AgentCore** sẽ sớm trở thành phần quan trọng trong ứng dụng doanh nghiệp → mình cần học sớm để đi trước.  
- **Data platform & governance** là chìa khóa → không chỉ code, mà còn quản lý dữ liệu đúng cách.  
- **AI-DLC** cho thấy vai trò của AI trong SDLC tương lai → có thể thử áp dụng dần trong project nhỏ.  
- **Security** không chỉ là add-on, mà phải thiết kế ngay từ đầu khi làm với GenAI.


#### Một số hình ảnh khi tham gia sự kiện

- Thêm các hình ảnh của các bạn tại đây
  > Tổng thể, sự kiện không chỉ cung cấp kiến thức kỹ thuật mà còn giúp tôi thay đổi cách tư duy về thiết kế ứng dụng, hiện đại hóa hệ thống và phối hợp hiệu quả hơn giữa các team.

