# 조동현 | DevOps & Cloud Engineer

<img align="left" width="150" alt="profile" src="https://github.com/user-attachments/assets/f6bfe9b4-6694-4789-b56a-01ce33d560dc" />

- 시스템의 근본 원리(OS, Network)를 파고들어 최적의 성능을 이끌어내는 DevOps 엔지니어 조동현입니다.
- 단순한 도구 활용을 넘어 **Docker(runc/Namespace), Nginx 아키텍처, Kernel System Call** 등 기술의 이면을 깊이 탐구하며 문제의 본질을 해결합니다.
- **Kubernetes(K8s)** 도입과 HPA 적용을 주도하여 가용성을 2.5배 향상시켰으며, **AWS 기반 데이터 파이프라인 최적화**를 수행했습니다.
- **AWS Cloud Club 초대 캡틴** 및 **300+ 포스트(13만+ 방문) 기술 블로그** 운영자로 리더십과 공유의 가치를 실천합니다.

<br>
<br>

---

## 📞 Contacts
- **✉️ Email:** mr8356@naver.com
- **🐱 Github:** https://github.com/mr8356
- **📄 Blog:** https://konkukcodekat.tistory.com/
- **🔗 LinkedIn:** http://www.linkedin.com/in/mr8356
- **🔗 Portfolio:** https://romantic-grin-797.notion.site/Donghyun-Jo-2a98683815268190be2bc39591142f38
- **Aws Cloud Club at Konkuk Meetup:** https://www.meetup.com/aws-cloud-club-at-konkuk-university/

---

## 🛠 Skills
- **Backend:** Java, Spring Boot
- **Cloud-Native:** AWS (Lambda, EKS, DynamoDB, RDS, EC2, Api-gateway, ELB, SQS), AWS CLI
- **Infrastructure:** Kubernetes, Docker, OpenStack, Nginx, Terraform(Basic)
- **Monitoring:** Prometheus, Grafana, Istio
- **CI/CD:** GitHub Actions
- **DB:** MySQL

---

## 🎓 Education
**건국대학교** | 컴퓨터공학부
> 2021.03 - 2027.02 (예정)

- **학점 :** 4.26 / 4.5
- **성적 우수 장학금 (Top 5%)**
  - 2024 2학기 Dean's List
  - 2025 1학기 Dean's List
  - 2025 2학기 President's List

---

## 🔬 Technical Deep-Dive
- https://konkukcodekat.tistory.com/372
- https://konkukcodekat.tistory.com/362
- https://konkukcodekat.tistory.com/367
- https://konkukcodekat.tistory.com/369
- https://konkukcodekat.tistory.com/370
- https://konkukcodekat.tistory.com/373

---

## 🚀 Projects & Activities

### Food Donor (공공데이터 기반 기부 플랫폼 웹서비스)
**"Serverless Architecture 기반의 비용 70% 절감 및 데이터 파이프라인 최적화"**
> **진행 기간 : 2025년 9월 ~ Present**

- **Role:** Cloud Architecture 설계 및 Backend 개발, IaC 구축(진행중)
- **Tech:** AWS Lambda, Athena, Glue, S3, EventBridge, Bedrock, SQS, Terraform
- **Links:** https://github.com/FoodDonorService/foodDonor-aws

<div align="center">
  <img width="100%" alt="Food Donor Architecture" src="https://github.com/user-attachments/assets/afdf7a21-e37d-41a3-b23f-25789dec5ff2" />
</div>

1. **FinOps 실천: 데이터 기반의 Serverless 전환 (비용 70% 절감)**
   - **[Analysis]** 간헐적 ETL 작업에 EC2는 비효율적이라 판단, **AWS Calculator**로 비용 시뮬레이션을 수행.
   - **[Decision]** **Serverless(Lambda, Athena)가 EC2 대비 70% 저렴함**을 수치로 증명하고, API Gateway와 Lambda 기반의 MSA 아키텍처를 구축하여 비용 효율과 유연성을 모두 확보
2. **Deep Dive: 대용량 처리 안정성 확보**
   - **[Problem]** 대용량 JSON 수집 과정에서 Lambda Runtime **OOM**(Out Of Memory) 발생.
   - **[Solution]** 비용이 드는 리소스 증설 대신, **Streaming 및 Chunking 기법**을 도입하여 로직 개선만으로 파이프라인 안정화
     - https://konkukcodekat.tistory.com/352
3. **Athena 쿼리 성능 및 비용 최적화 (비용 90% 절감)**
   - **[Optimization]** Athena 과금 모델(스캔 데이터양)을 분석하여 비용 누수 지점을 발견
   - **[Result]** Glue를 통해 데이터를 `Parquet`로 변환하고 `S3 Partitioning`을 적용, 불필요한 스캔을 차단하여 **쿼리 비용을 90% 절감**
     - https://konkukcodekat.tistory.com/353
4. **Legacy 인프라의 Terraform IaC 전환 (Reverse Engineering)**
   - **[Modernization] Former2**를 활용해 콘솔 기반 인프라를 **리버스 엔지니어링**하고, 하드코딩 제거 및 모듈화를 수행, S3 Backend 구축

---

### CashTicket (고가용성 티켓팅 웹서비스)
**"Kubernetes 기반의 오토스케일링 환경 구축 및 2.5배 성능 향상"**
> **진행 기간 : 2024년 12월 ~ 2025년 6월**

- **Role:** Infrastructure Lead & Backend Engineer
- **Tech:** Kubernetes, Java, Spring Boot, Redis
- **Links:** https://github.com/mr8356/cash_ticket

<div align="center">
  <img width="100%" alt="CashTicket Architecture" src="https://github.com/user-attachments/assets/02b555d9-bd27-46b4-b368-e39ab9d81648" />
</div>

1. **Kubernetes 인프라 구축 및 운영 (Ownership)**
   - **[Challenge]** 단일 서버 구조로는 트래픽 스파이크 시 서비스 안정성을 보장할 수 없다고 판단. 높은 러닝 커브에도 불구하고, **직접 Kubernetes 클러스터를 구축**하고 운영 환경을 표준화하여 **고가용성(HA) 아키텍처**를 완성
   - **[Result]** HPA(Horizontal Pod Autoscaler)를 적용하여 트래픽 변동에 유연하게 대응하는 시스템을 구축
2. **Redis 대기열 시스템을 통한 트래픽 제어**
   - **[Optimization]** 선착순 이벤트 시 DB Connection 고갈 방지를 위해 **Redis `Sorted Set`**을 활용. **조회 복잡도를 O(log N)으로 유지**하며 대기열 시스템을 설계해 고성능을 확보.
   - **[Performance]** 진입 유량 제어(Flow Control)를 통해 시스템 다운을 방지하고, Locust 부하 테스트 결과 **기존 대비 2.5배의 트래픽 처리량(Throughput)**을 달성.
3. **데이터 정합성 및 코드 품질 확보**
   - **[Reliability]** Spring Scheduler(CronJob)를 도입하여 만료된 티켓을 주기적으로 정리, 데이터 정합성을 확보. 또한 정기적인 **Code Review**를 주도하여 팀의 기술적 부채를 최소화.

---

### Roomie (SOPT 쉐어하우스 중계 플랫폼)
**"Event-Driven Architecture 도입으로 시스템 결합도 최소화"**
> **진행 기간 : 2024년 12월 ~ 2025년 6월**

- **Role:** Server Lead & Architect
- **Tech:** Spring Boot, Redis MQ, Docker, GitHub Actions
- **Links:** https://github.com/WeAreRoommies/Roomie-Server?tab=readme-ov-file

<div align="center">
  <img width="100%" alt="Roomie Architecture" src="https://github.com/user-attachments/assets/70b95be7-3e06-4792-ac3d-b470713c8bdc" />
</div>

1. **EDA 도입을 통한 병목 해결**
   - **[Issue]** 동기(Synchronous) 방식의 '입주 신청' 프로세스에서 트래픽 급증 시 **장애 전파 및 Latency 문제**가 발생함을 확인.
   - **[Architecting]** "알림의 즉시성보다 시스템 안정성이 우선"이라는 **비즈니스 요구사항(Requirements)을 정의**하고, **Redis MQ 기반의 EDA**를 도입.
   - **[Result]** 핵심 로직과 부가 로직을 비동기로 분리하여 결합도를 낮추고, nGrinder 부하 테스트 기준 **쓰기 처리량을 1.5배 향상**. (`nGrinder` 기준).
2. **CI/CD 파이프라인 구축**
   - **[Automation]** 반복적인 수동 배포로 인한 **운영 비효율을 제거**하고자 함.
   - **[Impact]** Docker와 GitHub Actions를 활용해 배포 파이프라인을 완전 자동화하여, **배포 시간을 단축하고 휴먼 에러를 방지**.

---

### DMS Lab 학부연구생 (하이브리드 클라우드 모니터링)
**"OpenStack 기반 프라이빗 클라우드 구축 및 모니터링 환경 확보"**
> **진행 기간 : 2024년 12월 ~ 2025년 2월**

- **Link:** https://dms.konkuk.ac.kr/people/DongHyun/
- **Blog:** https://konkukcodekat.tistory.com/356

1. **IaaS 환경 구축 및 딥다이브**
   - **[Action]** 클라우드 가상화 원리를 깊이 이해하기 위해, 베어메탈 환경에서 **OpenStack을 활용해 프라이빗 클라우드를 직접 구축**
   - **[Outcome]** OpenStack 스터디를 조직/주도하며 IaaS 환경 구축 완료, 전 과정을 **기술 블로그 오픈스택, 쿠버네티스 카테고리에** 상세 기록.
2. **Observability 확보**
   - **[Problem]** 구축된 인프라 내부 상태를 파악할 관측(Observability) 수단 부재.
   - **[Solution]** **Prometheus와 Grafana**를 연동, 하이브리드 클라우드 환경에 대한 실시간 모니터링 대시보드를 구축하여 운영 가시성을 확보.

---

## 👥 개발 동아리/대외 활동

### Amazon Web Services (AWS) | Cloud Club Captain
> *2025.11 - Present*

- 건국대학교 **초대 AWS Cloud Club 캡틴**으로 선정 (Founding Captain).
- [meet up link](https://www.meetup.com/aws-cloud-club-at-konkuk-university/)

### KUIT (대학생 IT 연합 동아리) | 6기 서버 파트장
> *2025.09 - Present*

- 실무 중심의 3주 단기 속성 서버 커리큘럼을 직접 설계 및 강의하며 엔지니어 양성에 기여.
- https://youtube.com/playlist?list=PL7z9i3yYqDwyQDKdaqjTQoFfEuPWlnztL&si=t4y4IzHrZTIUW0Cn

### Bibimbap (건국대 학술 동아리) | 회장
> *2025.01 - 2025.12*

- 깃사용법, SW 아키텍처, 클라우드 시스템 아키텍처, 마이크로서비스 아키텍처, 모니터링, SA 주제로 주간 세미나 총 15주차 30시간 주도.
- https://konkukcodekat.tistory.com/category/My%20seminar/Bibimbap%28President%29

### SOPT (대학생 IT 연합 동아리) | 35기 서버 파트 부원
> *2024.09 - 2025.02*

- **2학년때 합류 직후** 공동 세미나, 해커톤, 데모데이 등 3개 주요 행사의 서버 리드로 발탁.
- 'Roomie' 프로젝트 서버 개발 리드.

---

## 🏆 Awards
- SOPT 35기 해커톤 최우수상
- SOPT 35기 데모데이 우수상
- 2025 여름방학 컴퓨터공학부 해커톤 우수상
