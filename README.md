# Donghyun Jo (조동현) | DevOps & System Engineer

<img align="left" width="150" alt="profile" src="https://github.com/user-attachments/assets/f6bfe9b4-6694-4789-b56a-01ce33d560dc" />

- A **systems-oriented DevOps Engineer** who goes beyond tool-level usage to dissect the internals:
    - **Kubernetes** networking at the **Linux kernel level** (iptables, route tables, conntrack, Calico CNI)
    - **Nginx event-driven architecture**, and kernel **system calls** to solve problems at their root.
    - **Prometheus TSDB internals**, optimizing **kernel writeback** and **WAL/mmap** to mitigate I/O spikes and ensure high-throughput zero-copy storage.

- Actively documenting the journey on a **tech blog with 300+ posts and 130K+ visitors**.

- Selected (Nov 2025) as the founding **AWS Cloud Club Captain** for Konkuk University.

---

## Contacts

**✉️ Email**  
> mr8356@naver.com

**🐱 Github**  
> https://github.com/mr8356

**📄 Blog**  
> [동현의 코딩여행 (konkukcodekat.tistory.com)](https://konkukcodekat.tistory.com/)

**LinkedIn**  
> http://www.linkedin.com/in/mr8356

---

## Skills

- **Language:** Java(Spring Boot), Python(PS), C(Device Driver)
- **Cloud-Native:** AWS (Lambda, EKS, DynamoDB, RDS, EC2, Api-gateway, ELB, SQS), AWS CLI
- **Infrastructure:** Kubernetes, Docker, OpenStack, Nginx, Terraform(Basic)
- **Monitoring:** Prometheus, Grafana, Istio
- **CI/CD:** GitHub Actions
- **DB:** MySQL

---

## Education

- **Konkuk University** | Computer Science & Engineering
- **Mar 2021 - Feb 2027 (Expected)**
- **GPA:** 4.26 / 4.5
- **Academic Excellence Scholarship (Top 5%)**
    - 2024 Fall Dean's List
    - 2025 Spring Dean's List
    - 2025 Fall President's List

---

## Technical Deep-Dive

- [[K8s] Kernel-Level Networking Analysis: Service VIP to Pod (iptables, route, Calico CNI IPIP Mode)](https://konkukcodekat.tistory.com/372)
- [[DevOps Interview Retrospective] TLB, K8s Internals & Kernel Isolation, TLS Handshake](https://konkukcodekat.tistory.com/362)
- [[DevOps Interview Retrospective #2] K8s Control Plane Scalability & Load, mTLS](https://konkukcodekat.tistory.com/367)
- [Limitations of Thread-Based Servers (C10K Problem) & Nginx Process Model for Reducing Context-Switching Overhead](https://konkukcodekat.tistory.com/369)
- [How Nginx Handles High-Volume Traffic via Non-blocking I/O Multiplexing & epoll System Calls](https://konkukcodekat.tistory.com/370)
- [[Nginx] Zero Copy (sendfile) Kernel Internals & System Call Tracing via strace](https://konkukcodekat.tistory.com/373)

---

## Projects & Activities

### **FinOps Consulting (RobotCom Startup AWS Infrastructure Cost Optimization)**

**"Zero-Downtime Migration & 87% Infrastructure Cost Reduction Without a Dedicated Server Admin"**

> **Period: Mar 2026 (Short-term Contract)**

- **Role:** FinOps Consultant — Infrastructure Diagnosis, Zero-Downtime Migration, Architecture Redesign
- **Tech:** AWS EC2, EBS, CloudWatch, EC2 Image Builder, ALB, VPC, S3, CloudFront, Route 53, ACM, IAM
- **Blog:** https://konkukcodekat.tistory.com/377
1. **FinOps in Practice: 83% EC2 Cost Reduction ($84 → $14)**
    - **[Analysis]** Proved overprovisioning of t2.large with CloudWatch CPU metrics (avg 1%, peak <20%).
    - **[Decision]** Persuaded the CEO to adopt t2→t3 migration + 3-year RI prepayment (ROI 165%), reducing monthly cost from **$84.10 → $14.30 (83% savings).**
2. **Deep Dive: Zero-Downtime EC2 Spec Downgrade**
    - **[Problem]** Server admin had resigned; stopping the instance risked unrecoverable service outage.
    - **[Solution]** EBS Snapshot → EC2 Image Builder AMI Pipeline → ALB switching achieved **0 minutes of downtime**. Worked around IAM Trust Policy omission and **vmie kernel version mismatch (6.8.0-1040-aws) bug via native AMI manual creation.**
3. **Over-Engineering Discovery & Serverless Migration**
    - **[Analysis]** Discovered 7 zombie EIPs via VPC ENI/ELB dependency analysis. Confirmed static HTML was being served via EC2+ALB.
    - **[Result]** Migrated to S3 + CloudFront CDN + ACM SSL + Route 53 Alias (Serverless). **Total infra cost: $115+/mo → $14/mo (87% reduction), saving $3,600+ over 3 years.**

---

### **Food Donor (Public Data-Driven Donation Platform Web Service)**

**"70% Cost Reduction & Data Pipeline Optimization via Serverless Architecture"**

> **Period: Sep 2025 - Present**

- **Role:** Cloud Architecture Design & Backend Development, IaC Implementation (In Progress)
- **Tech:** AWS Lambda, Athena, Glue, S3, EventBridge, Bedrock, SQS, Terraform
- **GitHub:** https://github.com/FoodDonorService/foodDonor-aws

<div align="center">
  <img width="100%" alt="Food Donor Architecture" src="https://github.com/user-attachments/assets/afdf7a21-e37d-41a3-b23f-25789dec5ff2" />
</div>

1. **FinOps in Practice: Data-Driven Serverless Migration (70% Cost Reduction)**
    - **[Analysis]** EC2 deemed inefficient for intermittent ETL workloads; performed cost simulation with **AWS Calculator**.
    - **[Decision]** Quantitatively proved **Serverless (Lambda, Athena) is 70% cheaper than EC2**, and built an MSA architecture based on API Gateway + Lambda for both cost efficiency and flexibility.
2. **Deep Dive: Ensuring Stability for Large-Scale Processing**
    - **[Problem]** Lambda Runtime **OOM** (Out Of Memory) during large-scale JSON ingestion.
    - **[Solution]** Instead of costly resource scaling, applied **Streaming & Chunking techniques** to stabilize the pipeline through logic optimization alone.
        - [[AWS Lambda] Streaming + Chunking to Resolve Runtime.OutOfMemory in Big Data Batch Pipeline](https://konkukcodekat.tistory.com/352)
3. **Athena Query Performance & Cost Optimization (90% Cost Reduction)**
    - **[Optimization]** Identified cost leakage by analyzing Athena's billing model (scanned data volume).
    - **[Result]** Converted data to **Parquet** via Glue and applied **S3 Partitioning**, blocking unnecessary scans to achieve **90% query cost reduction**.
        - [[AWS Glue] PySpark: Converting Streamed Split JSON to Columnar Data via Parquet + Partitioning](https://konkukcodekat.tistory.com/353)
4. **Legacy Infrastructure → Terraform IaC Migration (Reverse Engineering)**
    - **[Modernization]** Reverse-engineered console-based infrastructure using **Former2**, removed hardcoding, modularized, and set up S3 Backend.

---

### **CashTicket (High-Availability Ticketing Web Service)**

**"2.5x Performance Improvement via Kubernetes-Based Auto-Scaling"**

> **Period: Dec 2024 - Jun 2025**

- **Role:** Infrastructure Lead & Backend Engineer
- **Tech:** Kubernetes, Java, Spring Boot, Redis
- **GitHub:** https://github.com/mr8356/cash_ticket

<div align="center">
  <img width="100%" alt="CashTicket Architecture" src="https://github.com/user-attachments/assets/02b555d9-bd27-46b4-b368-e39ab9d81648" />
</div>

1. **Kubernetes Infrastructure Setup & Operations (Ownership)**
    - **[Challenge]** Single-server architecture could not guarantee service stability during traffic spikes. Despite the steep learning curve, personally built and operated a **Kubernetes cluster** to establish a **high-availability (HA) architecture**.
    - **[Result]** Applied HPA (Horizontal Pod Autoscaler) to build a system that flexibly responds to traffic fluctuations.
2. **Redis Queue System for Traffic Control**
    - **[Optimization]** Used **Redis** **Sorted Set** to prevent DB connection exhaustion during first-come-first-served events, maintaining **O(log N) lookup complexity** for high-performance queue design.
    - **[Performance]** Prevented system downtime via flow control; Locust load testing showed **2.5x improvement in throughput** over baseline.
3. **Data Consistency & Code Quality Assurance**
    - **[Reliability]** Introduced Spring Scheduler (CronJob) for periodic cleanup of expired tickets to ensure data consistency. Led regular **Code Reviews** to minimize technical debt.

---

### Roomie (SOPT Share-House Brokerage Platform)

**"Minimized System Coupling via Event-Driven Architecture"**

> **Period: Dec 2024 - Jun 2025**

- **Role:** Server Lead & Architect
- **Tech:** Spring Boot, Redis MQ, Docker, GitHub Actions
- **GitHub:** [Roomie-Server (github.com/WeAreRoommies/Roomie-Server)](https://github.com/WeAreRoommies/Roomie-Server?tab=readme-ov-file)

<div align="center">
  <img width="100%" alt="Roomie Architecture" src="https://github.com/user-attachments/assets/70b95be7-3e06-4792-ac3d-b470713c8bdc" />
</div>

1. **Bottleneck Resolution via EDA Adoption**
    - **[Issue]** Synchronous move-in application process caused **cascading failures and latency spikes** under high traffic.
    - **[Architecting]** Defined business requirement: "System stability takes priority over notification immediacy." Introduced **Redis MQ-based EDA**.
    - **[Result]** Decoupled core logic from auxiliary logic asynchronously, reducing coupling and achieving **1.5x improvement in write throughput** (`nGrinder` benchmark).
2. **CI/CD Pipeline Implementation**
    - **[Automation]** Aimed to eliminate **operational inefficiency** from repetitive manual deployments.
    - **[Impact]** Fully automated the deployment pipeline using Docker and GitHub Actions, **reducing deployment time and preventing human errors**.

---

### DMS Lab — Undergraduate Researcher (Hybrid Cloud Monitoring)

**"Built Private Cloud on OpenStack & Established Observability Environment"**

- **Lab Page:** [DongHyun Jo (dms.konkuk.ac.kr)](https://dms.konkuk.ac.kr/people/DongHyun/)
- **Blog:** [K8s Monitoring: Troubleshooting NetworkPolicy Firewall & ServiceMonitor Issues with Separate Helm Charts for Loki and Prometheus](https://konkukcodekat.tistory.com/356)

> **Period: Dec 2024 - Feb 2025**

1. **IaaS Environment Setup & Deep Dive**
    - **[Action]** To deeply understand cloud virtualization principles, built a **private cloud from bare-metal using OpenStack**.
    - **[Outcome]** Organized and led an OpenStack study group; completed IaaS environment setup and documented the entire process on **technical blog (OpenStack & Kubernetes categories)**.
2. **Observability**
    - **[Problem]** No observability tooling to understand the state of the deployed infrastructure.
    - **[Solution]** Integrated **Prometheus and Grafana** to build a real-time monitoring dashboard for the hybrid cloud environment.

---

## Extracurricular Activities

### Amazon Web Services (AWS) | Cloud Club Captain

*2025.11 - Present*

- Selected as the **inaugural AWS Cloud Club Captain** at Konkuk University (Founding Captain).

### KUIT (University IT Club) | 6th Gen. Server Part Lead

*2025.09 - Present*

- Designed and delivered a practice-oriented intensive 3-week server curriculum, contributing to engineer training.
- https://youtube.com/playlist?list=PL7z9i3yYqDwyQDKdaqjTQoFfEuPWlnztL&si=t4y4IzHrZTIUW0Cn

### Bibimbap (Konkuk Academic Club) | President

*2025.01 - 2025.12*

- Led 15-week, 30-hour weekly seminars covering Git, SW Architecture, Cloud Systems, Microservices Architecture, Monitoring, and SA.
- [https://konkukcodekat.tistory.com/category/My seminar/Bibimbap(President)](https://konkukcodekat.tistory.com/category/My%20seminar/Bibimbap%28President%29)

### SOPT (University IT Club) | 35th Gen. Server Part Member

*2024.09 - 2025.02*

- **Immediately after joining as a sophomore**, selected as server lead for 3 major events: Joint Seminar, Hackathon, and Demo Day.
- Led server development for the 'Roomie' project.

---

## Awards

- SOPT 35th Hackathon — Grand Prize
- SOPT 35th Demo Day — Excellence Award
- 2025 Summer CS Department Hackathon — Excellence Award
