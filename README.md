# 이승준 (Seung-jun Lee)

한양대학교 ERICA 컴퓨터공학 전공, 클라우드 부전공
<br>Hanyang University ERICA, B.S. in Computer Science (minor in Cloud Computing)

## 기술 스택 / Tech Stack

| 분야 / Area | 사용 기술 / Technologies |
| --- | --- |
| Cloud (AWS) | EC2, ECS Fargate, RDS, S3, SQS, Lambda, EventBridge Scheduler, Secrets Manager, IAM |
| Cloud (Azure) | Virtual Machines, App Service, Functions, Cosmos DB |
| Container / CI | Docker, Docker Compose, GitHub Actions, LocalStack |
| Backend | Go, Python (FastAPI), Java (Spring Boot) |
| Frontend | React, Vite |
| Database | PostgreSQL |

## 프로젝트 / Projects

### 1. CloudQueue — Go와 AWS로 만든 비동기 작업 처리 플랫폼 (개인)
**CloudQueue — Asynchronous job-processing platform with Go and AWS (personal)**

[lsz09/lsz-go-project](https://github.com/lsz09/lsz-go-project)

- 로그 파일 처리 요청을 API 서버가 받아 SQS로 넘기고, Worker가 비동기로 분석해 결과를 S3에 저장
  <br>The API server queues file-processing jobs on SQS; workers analyze them asynchronously and store results in S3
- 원자적 UPDATE로 여러 Worker가 같은 작업을 가져가도 하나만 처리, 성공한 메시지만 삭제, DLQ와 Visibility Timeout 자동 연장
  <br>Atomic state transitions, delete-on-success, DLQ, and visibility-timeout heartbeats
- LocalStack으로 비용 없이 SQS·S3를 개발하고, GitHub Actions에서 단위·통합 테스트 자동 실행
  <br>Developed against LocalStack at no cost; unit and integration tests run in GitHub Actions
- `Go` `PostgreSQL` `SQS` `S3` `LocalStack` `Docker Compose` `GitHub Actions`

### 2. 캡스톤 디자인 — 영어 지문 분석 앱의 서버 구축 (4인 팀, 팀장)
**Capstone Design — Server infrastructure for an English-passage analysis app (team of 4, team lead)**

[capstone-backend](https://github.com/CapstoneTeamRunning/capstone-backend) · [capstone-webview](https://github.com/CapstoneTeamRunning/capstone-webview)

- AWS EC2 한 대에 PostgreSQL, React, FastAPI 세 개의 Docker 컨테이너를 띄우고 서로 통신할 수 있게 연결
  <br>Ran PostgreSQL, React, and FastAPI as three Docker containers on a single EC2 instance and connected them
- 비용을 줄이기 위해 EC2 한 대 구성을 선택 (예산이 있으면 ECS·RDS로 분리하는 구성도 검토)
  <br>Chose a single-instance setup to keep costs down, with an ECS + RDS design considered for a larger budget
- 프론트엔드와 백엔드가 연결되지 않던 문제를 로그와 pgAdmin으로 확인하며 해결해 하나의 앱으로 완성
  <br>Debugged the frontend–backend connection using logs and pgAdmin and shipped the app as one system
- `AWS EC2` `Docker` `FastAPI` `React` `PostgreSQL`

### 3. HSA (Hanyang Support Agent) — AI 고객 응대 자동화 시스템 (팀)
**HSA — AI customer-support automation system (team)**

[Hanyang-Support-Agent/hsa-server](https://github.com/Hanyang-Support-Agent/hsa-server)

- AI가 문의를 분류하고 답변 초안을 만들면 관리자가 검토해 보내는 시스템
  <br>AI classifies inquiries and drafts replies; an administrator reviews and sends them
- Spring Boot 백엔드 서버를 AWS ECS에 올리는 배포 작업에 참가
  <br>Took part in deploying the Spring Boot backend to AWS ECS
- `Spring Boot` `AWS ECS Fargate` `RDS (PostgreSQL)` `GitHub Actions`

### 4. AI 자동 블로그 — 서버리스로 매일 글 자동 게시 (클라우드 아키텍처 수업)
**AI Auto-Blog — Serverless daily posting (Cloud Architecture course)**

[lszbbicam09.blogspot.com](https://lszbbicam09.blogspot.com/)

- EventBridge Scheduler로 매일 같은 시간에 Lambda를 실행하고, 함수에 있는 프롬프트를 OpenAI GPT API로 보내 받은 글을 블로그에 자동 게시
  <br>EventBridge Scheduler triggers Lambda daily; Lambda sends a prompt to the OpenAI GPT API and posts the result to a blog
- 2026년 5~7월에 클라우드·데이터베이스·OS 등 IT 주제의 일본어 글을 매일 자동 게시
  <br>Automatically published daily Japanese articles on IT topics (cloud, databases, operating systems) from May to July 2026
- API 키는 Secrets Manager로 관리
  <br>API keys managed with Secrets Manager
- `AWS Lambda` `EventBridge Scheduler` `Secrets Manager` `OpenAI API`

### 5. Azure 실습 — 클라우드 응용 SW 개발 수업
**Azure Labs — Cloud Application Development course**

- Azure 가상 머신, App Service, Functions, Cosmos DB를 써서 웹앱 공개와 데이터베이스 연동 실습
  <br>Deployed web apps and connected databases using Azure VMs, App Service, Functions, and Cosmos DB
- `Azure` `App Service` `Functions` `Cosmos DB`
