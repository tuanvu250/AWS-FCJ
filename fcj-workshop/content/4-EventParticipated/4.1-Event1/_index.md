---
title: "Event 1"
date: "2025-09-09"
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---


# Summary Report: “GenAI & Data”

### Event Objectives

- Update on **GenAI trends and strategies** on AWS  
- Learn how to **build a unified data foundation** for AI/Analytics  
- Introduction to the **AI-Driven Development Lifecycle (AI-DLC)** in software development  
- Gain insights into **security for GenAI applications** and the role of **AI Agents in enterprises**

### Speakers

- **Jun Kai Loke** – AI/ML Specialist SA, AWS  
- **Kien Nguyen** – Solutions Architect, AWS  
- **Tamelly Lim** – Storage Specialist SA, AWS  
- **Binh Tran** – Senior Solutions Architect, AWS  
- **Taiki Dang** – Solutions Architect, AWS  
- **Michael Armentano** – Principal WW GTM Specialist, AWS 

### Key Highlights

#### 1. Building a Unified Data Foundation on AWS for AI & Analytics
- Strategies for constructing a unified, scalable data foundation for AI/Analytics.  
- End-to-end data pipeline: ingestion → storage → processing → access → governance.  
- Overcoming 3 silos (Data/People/Business); enable self-service with standardized governance.  
- Core services: **S3, Glue, Redshift, Lake Formation, OpenSearch, Kinesis/MSK**.

#### 2. Building the Future: GenAI Adoption Strategy on AWS
- Vision and trends of GenAI; roadmap for enterprise adoption.  
- **Amazon Bedrock**: model choice, customization/RAG, guardrails, cost/latency optimization.  
- **AgentCore**: framework-independent runtime, tool integration gateway, identity & observability.  
- **Amazon Nova** and ecosystem frameworks (**CrewAI, LangGraph, LlamaIndex, Strands**).

#### 3. Securing Generative AI Applications with AWS
- Risks per **OWASP LLM (LLM01/02)**; ensuring safe output handling.  
- Security at multiple layers: **infrastructure, models, applications**; IAM, encryption, zero-trust, continuous monitoring.  
- **5 Security Pillars**: Compliance & Governance, Legal & Privacy, Controls, Risk Management, Resilience.  
- **Generative AI Security Scoping Matrix (Scope 1 → 5)**: from consumer apps to self-trained models.  
- **Bedrock Guardrails**: filter sensitive content with configurable thresholds.  
- **Human-in-the-loop**: human approval/intervention when needed.  
- **Observability (OpenTelemetry)**: transparent monitoring, logging, and tracing of AI behaviors.

#### 4. Beyond Automation: AI Agents as Productivity Multipliers
- Agentic AI: from assistants → multi-agent systems; less human oversight, more autonomy.  
- Applications: customer support, BI with **Amazon Q (QuickSight)**, workflow automation.  
- **Amazon Q in QuickSight**: Build Dashboards/Reports, Data Q&A, Executive Summaries.  
- Expected value: **exponential productivity gains**; requires strong data foundation & governance.

#### 5. Reliability and Veracity of GenAI
- Challenge of **hallucination** → mitigated via Prompt Engineering, RAG, Fine-tuning, Parameter Tuning.  
- **RAG in action**: user input → embeddings → contextual retrieval → LLM → grounded response.  

#### 6. AI-Driven Development Lifecycle (AI-DLC)
- An **AI-centric** lifecycle: Inception → Construction → Operation.  
- Evolution: **AI-Assisted → AI-Driven → AI-Managed**; AI orchestrates, humans approve.  
- Deployment infrastructure: **IaC, automated testing, observability, risk management**.

#### 7. Amazon SageMaker (Unified Studio – Next Gen)
- **One unified environment** for **data, analytics, and AI**: SQL analytics, data processing, model development/training, **GenAI app development**, BI, streaming, search analytics.  
- **Lakehouse + Governance**: catalog/lineage, policy-based access, auditing; unified **Data & AI governance**.  
- **Zero-ETL integration**: core **S3 ↔ Redshift**, connections to **Aurora, DynamoDB, RDS, OpenSearch, Kinesis/MSK, Salesforce, SAP, ServiceNow**.  
- **Full MLOps**: pipelines/experiments, model registry, deployment endpoints, **Feature Store**, monitoring.  
- **Integrated with Bedrock & JumpStart**: access to foundation models (via Bedrock), reference solutions, and accelerated deployment on SageMaker.

- **SDLC automation**: From planning to maintenance
- **Code transformation**: Java upgrade, .NET modernization
- **AWS Transform agents**: VMware, Mainframe, .NET migration

### Key Takeaways

#### Design Mindset
- **Business-first approach**: Always start from business needs, not technology.  
- **Ubiquitous language**: The importance of shared vocabulary between business and tech, especially in teamwork and communication with mentors.  
- **Bounded contexts**: Understanding how to partition domains to avoid complexity when scaling.

#### Architecture & Technology
- **Unified Data Foundation**: ingestion → storage → processing → access → governance.  
- **GenAI on AWS**: Bedrock (model choice, guardrails, RAG), AgentCore (runtime, gateway, identity, observability), Nova LLMs.  
- **AI Agents**: from assistants → multi-agent systems; real-world use cases like customer support and BI with Amazon Q.  
- **AI-DLC**: AI as the core collaborator in SDLC (Inception → Construction → Operation).  
- **Security-first mindset**: Guardrails, human-in-the-loop, governance & monitoring (OpenTelemetry).

#### Strategy & Application
- **Phased approach**: Avoid rushing; need a clear roadmap for modernization & AI adoption.  
- **Zero-ETL & Unified Studio (SageMaker)**: Simplify data integration, centralize AI lifecycle management.  
- **ROI measurement**: Not just cost savings, but agility and productivity.

### Applying to Work

- **In my project**:  
  - Experiment with **AI Agents** for workflows like registration/login or customer support.  
  - Apply **validation/guardrails** to ensure safe integration of GenAI features.  

- **In team projects (Sprint 0, serverless vs containerization)**:  
  - Apply **AI-DLC** principles to split tasks logically: AI supports research/code generation, team reviews & approves.  
  - Understand when to use **Lambda (serverless)** vs **ECS/Fargate (containers)**.  

- **In my learning path**:  
  - Recognize the need for a **business-first approach** when writing documents and gathering requirements.  
  - Acknowledge that a strong **data foundation** is critical for any successful GenAI application.

### Event Experience

- Learned directly from AWS experts on **Data, GenAI adoption, Security, AI Agents, and AI-DLC**.  
- Slides and case studies gave me a clear picture of how **AgentCore** works in real-world scenarios.  
- Understood how **AWS envisions the future of software development**: AI not just as an assistant but as a core lifecycle component.  
- Realized that successful GenAI adoption requires **solid data foundation + strong security + structured strategy**.

---

### Lesson learned

- **AI Agents** and **AgentCore** will soon become critical in enterprise applications → I should learn early to stay ahead.  
- **Data platform & governance** are essential → not just coding, but also managing data properly.  
- **AI-DLC** highlights AI’s role in future SDLC → I can experiment with small projects now.  
- **Security** is not an afterthought; it must be built into GenAI systems from the start.

#### Some event photos

_Add your event photos here_

> Overall, the event not only provided technical knowledge but also helped me reshape my thinking about application design, system modernization, and cross-team collaboration.
