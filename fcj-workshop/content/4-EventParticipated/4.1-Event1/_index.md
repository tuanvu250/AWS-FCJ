---
title: "Event 1"
date: "2025-09-09"
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

# Gen AI & Data

---

## 1. Evolution of Agentic AI

- **Generative AI Assistants**: Follow rules, automate repetitive tasks.
- **Generative AI Agents**: Achieve single goals, broader tasks, automate workflows.
- **Agentic AI Systems**: Fully autonomous, multi-agent collaboration, mimic human logic.
- Trend: Moving from *more human oversight* → *less human oversight*.

---

## 2. Value Creation with Agentic AI

- **Workplace productivity**
- **Business workflows**
- **Innovation and research**

---

## 3. Market Trends

- By **2028**, 33% of enterprise software apps will use Agentic AI (vs <1% in 2024).
- By **2030**, 15% of daily work decisions will be made autonomously by Agentic AI.
- **Challenge**: 40% of projects may fail by 2027 due to unclear value, high cost, or poor risk control.

---

## 4. Vietnam Data & AI Success Stories

- **Katalon**: Agentic QA (automation testing with intelligent agents).
- **Apero**: AI adoption with NVIDIA GPUs (50M+ downloads).
- **Techcom Securities**: Multi-agent analysis for market & investment.

---

## 5. AWS AI Platforms

### Amazon Bedrock

- Build and scale GenAI apps quickly.
- Features: Model choice, cost optimization, safety, orchestration.

### Amazon Bedrock AgentCore

- **Purpose**: Deploy and manage production-ready agents securely at scale.
- **Capabilities**:
  - Agent runtime & identity
  - Tool discovery & integration
  - Short-term & long-term memory
  - Debugging, tracing, monitoring
  - Code interpretation & browser automation
- **Runtime**:
  - Framework & model independent (supports Strands, LangChain, CrewAI…)
  - Use-case independent (large payloads: text, audio, video)
  - Enterprise-grade isolation (session isolation, authentication, observability)
- **Gateway**:
  - Simplifies tool integration (REST APIs, Lambda)
  - Secure, unified tool access
  - Intelligent discovery via MCP + semantic search
- **Identity**:
  - Secure access with enterprise identity providers
  - Reduced consent fatigue (streamlined flows)
  - Inbound/outbound authentication (OAuth2, IAM, Cognito)
- **Observability**:
  - Full transparency of agent behavior
  - Enterprise security & governance (IAM, PII redaction)
  - Integration with 3rd-party observability tools (OTEL)
- **Customer Support Agent Example**:
  - Workflow: Customer → Bedrock LLM → Support Agent → AgentCore Gateway → Lambda tools (warranty check, profile retrieval).

### Amazon Nova (LLM family)

- Models: Pro, Lite, Micro, Act, Sonic, Premier.
- Covers text, speech, video QA.

### Frameworks for Agents

- CrewAI, LangGraph, LlamaIndex, Strands Agents SDK.
- **Strands Agents v1.0**: A2A support, conversation persistence, multi-agent workflows.

---

## 6. AI Agent Concepts

- **Definition**: Autonomous software systems leveraging AI to reason, plan, and complete tasks on behalf of humans/systems.
- **Components**: Goals, tools, context, observation, actions.
- **Challenge**: Heavy lifting in production (security, past interactions, access control, auditing).
- **Types of Agents**:
  - Specialized: Amazon Q agents.
  - Fully-managed: Bedrock agents with orchestration.
  - DIY: Expert developers using open frameworks.
- **Memory**:
  - Short-term: chat messages, session state.
  - Long-term: semantic, preferences, summaries.
  - Automatic extraction module for efficiency.

---

## 7. Data & Analytics Foundation

### Data Challenges

- Silos: **Data, People, Business**.
- Evolving requirements: From structured → unstructured, vector DBs, self-service governance.

### Metadata & AI

- Data prep → Metadata → Analytics & AI (GenAI/RAG, recommendations, anomaly detection).

### AWS Database Services

- **Relational**: RDS, Aurora.
- **Specialized**: DynamoDB, DocumentDB, ElastiCache, Neptune, Timestream, QLDB, Keyspaces, MemoryDB.

### Vector Search

- Available in DocumentDB, DynamoDB, MemoryDB, Neptune, OpenSearch, Aurora, RDS.

### AWS Analytics Services

- Athena, EMR, Kinesis, Redshift, Glue, QuickSight, OpenSearch.

---

## 8. Amazon SageMaker (Next Gen)

- **Unified Studio**: One environment for data, analytics, and AI.
- **Features**: SQL analytics, data processing, model & GenAI app development, BI, streaming, search analytics.
- **Governance**: Data & AI policies.
- **Lakehouse** foundation.

---

## 9. Data Integration: Zero-ETL

- **Amazon S3 + Redshift** as core.
- Integrations with Aurora, DynamoDB, RDS, MSK, Kinesis, OpenSearch, Salesforce, SAP, ServiceNow.

---

## 10. AI-Driven Development Lifecycle (AI-DLC)

### Challenges of AI-Assisted Development

- Still manual heavy lifting.
- AI applied narrowly.
- **Limitations**:
  - Not delivering agility promise.
  - Manual inefficiencies.
  - Technical debts.

### From AI-Assisted → AI-Driven → AI-Managed

- **AI-Assisted**: Support coding, but humans still manage planning & validation.
- **AI-Driven**: AI orchestrates planning, task decomposition, architectural suggestions.
- **AI-Managed**: Fully automated, humans only validate and approve.

### Lifecycle Stages

1. **Inception**
   - Build context on existing code.
   - Elaborate intent with user stories.
   - Plan with units of work.
2. **Construction**
   - Domain model (component model).
   - Generate code & test.
   - Add architectural components.
   - Deploy with IaC & tests.
3. **Operation**
   - Deploy in production with IaC.
   - Manage incidents.

### AI vs Users Roles

- **AI**: Research & plan, build & test, deploy.
- **Users**: Decisions, reviews, approvals.

### Unicorn Gym

- **Mechanics**: Align – Experience – Adapt – Scale.
- **Pre-Requisites**:
  - Preparing code repository.
  - List of problem statements (greenfield/brownfield, new features, technical debt).
  - Leadership attendance for kickoff & demo.

---

## 11. Security in Generative AI

### Key Pillars

- **Compliance & Governance**: Usage guidelines, monitoring, reporting.
- **Legal & Privacy**: Control of data, encryption, privacy standards.
- **Controls**: Human-in-the-loop, explainability, testing strategy, IAM.
- **Risk Management**: Threat modeling, third-party risk assessments.
- **Resilience**: Data management, high availability, disaster recovery.

### Security Scoping Matrix

- **Scope 1**: Consumer apps (ChatGPT, MidJourney).
- **Scope 2**: Enterprise SaaS apps (Salesforce Einstein GPT, Amazon Q).
- **Scope 3**: Pre-trained models with versioning.
- **Scope 4**: Fine-tuned models.
- **Scope 5**: Self-trained models (Amazon SageMaker).

### Application Risks

- **LLM01**: Prompt injection.
- **LLM02**: Insecure output handling.
- Risks in plugins/extensions, downstream services, data pipelines.

### Mitigation Strategies

- Secure prompts, guardrails, access control.
- Use &lt;thinking&gt; and &lt;answer&gt; tags.
- Contextual multi-perspective prompts.
- Data sanitization & supply chain verification.
- Human-in-the-loop for validation.

### Veracity (Hallucination)

- False outputs due to incomplete/incorrect context.
- **Mitigation**: Prompt engineering, RAG, fine-tuning, inference parameter tuning.

### RAG (Retrieval-Augmented Generation)

- Process: User input → Embedding → Prompt augmentation → LLM → Response.
- Supports grounded, context-rich answers.

### Bedrock Guardrails

- Content filtering by category (toxic, violence, sexual, etc.).
- Configurable thresholds for enterprise policies.

---

## 12. Amazon Q & Agentic AI for BI

### What are AI Agents?

- Autonomous systems that reason, plan, execute tasks.

### Choices of Agents

- **Specialized**: Amazon Q agents for productivity.
- **Fully-Managed**: Bedrock agents with orchestration.
- **DIY**: Open-source frameworks.

### Amazon Q in QuickSight

- **Dashboards & Reports**: Build visuals, refine calculations.
- **Data Q&A**: Ask natural language questions.
- **Summaries & Stories**: Generate insights, documents, presentations.

### Agentic AI Scenarios by Amazon Q

- Step-by-step analysis for complex BI tasks.
- Multi-modal AI agents reduce manual work.
- Extensible for reusability.

---

## 13. Final Takeaways

- AWS AI vision spans **data → model → agent → governance**.
- **AgentCore** enables production-grade agent orchestration.
- **AI-DLC** reshapes SDLC with AI as core collaborator.
- **Security-first mindset** is essential for generative AI adoption.
- **Amazon Q** empowers business users with natural language BI.