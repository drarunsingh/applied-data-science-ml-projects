# Intelligent Retail Management using Hybrid LLM and SQL Architecture
**Conversational Business Intelligence with Agentic Workflows**

---

## 1. Project Overview

Small and medium-sized retail businesses often struggle to extract actionable insights from their operational data due to the rigidity and technical complexity of traditional ERP systems. Business owners typically depend on predefined dashboards or manual SQL queries, which limits their ability to perform ad-hoc analysis.

This project presents an **Intelligent Retail Management Assistant** that enables **natural language interaction with structured enterprise data** using a **hybrid Large Language Model (LLM) and SQL-based architecture**. The system allows non-technical users to query inventory, sales, and supply-chain data using everyday English, while ensuring strict numerical accuracy.

---

## 2. Problem Statement

While Large Language Models offer powerful conversational capabilities, they are inherently unreliable for domains requiring exact numerical correctness, such as:

- Financial reporting  
- Inventory management  
- Sales analytics  

Purely generative models risk hallucinating values, which is unacceptable in operational settings.

### Objective

To design a **context-aware, agentic system** that:
- Preserves deterministic accuracy for database queries
- Leverages LLMs for interpretation and synthesis
- Separates reasoning, retrieval, and action execution

---

## 3. System Architecture

The system follows a **modular agent-based architecture**, ensuring scalability, safety, and interpretability.

### Core Components

#### 1️⃣ Intent Router
- Acts as the system entry point
- Classifies user queries into:
  - Normal conversational queries
  - Database-related queries
  - Action-oriented requests (email, workflows)

#### 2️⃣ Database Agent (Text-to-SQL Pipeline)
- Converts natural language queries into structured SQL
- Uses Retrieval-Augmented Generation (RAG) by injecting database schema context
- Executes queries via ORM to ensure:
  - Type safety
  - Protection against SQL injection

#### 3️⃣ Action Agent
- Orchestrates multi-step workflows
- Combines retrieved data with LLM reasoning
- Produces final, context-aware responses

#### 4️⃣ Autonomous Email Agent
- Continuously monitors incoming emails
- Identifies registered users
- Generates context-aware responses using LLMs
- Logs all interactions for auditability

---

## 4. Data Flow

1. User submits a natural language query via chat interface  
2. Intent Router classifies the request  
3. For data-driven queries:
   - Database Agent generates and executes SQL
   - Results returned as structured JSON
4. Action Agent performs synthesis using LLM
5. Final response returned to the user

This clear separation ensures **numerical correctness without sacrificing conversational flexibility**.

---

## 5. Technology Stack

- **Backend:** Python, FastAPI
- **Frontend:** React (Vite + Tailwind CSS)
- **Database:** PostgreSQL
- **ORM:** SQLAlchemy
- **LLM:** GPT-4-class models
- **Email Integration:** Gmail API
- **Architecture Style:** Agentic / Microservices

---

## 6. Use Case Demonstrations

### Sales Performance Analysis
- Query: *“Provide a detailed analysis on the top three products based on sales”*
- System:
  - Generates SQL with joins and aggregations
  - Produces contextual business insights
  - Distinguishes high-volume vs high-value products

### Inventory Monitoring
- Query: *“Check for inventory items below 5 units”*
- System:
  - Translates threshold constraints into SQL WHERE clauses
  - Identifies low-stock items across categories
  - Enables proactive restocking decisions

---

## 7. Results and Observations

- Accurate translation of natural language into executable SQL
- Zero hallucination of numerical values
- High-quality synthesis of raw data into executive-level insights
- Effective separation of deterministic and generative responsibilities

The system demonstrates that **LLMs can safely augment enterprise BI systems when properly constrained**.

---

## 8. Key Contributions

- Hybrid LLM + SQL architecture for enterprise BI
- Agent-based design with strict responsibility separation
- Secure Text-to-SQL pipeline using ORM
- Autonomous email handling for operational workflows
- Scalable and extensible system design

---

## 9. Limitations

- Currently focused on descriptive analytics
- Requires schema updates when database evolves
- Dependent on prompt quality for intent classification
- Not designed for high-frequency transactional workloads

---

## 10. Future Work

- Predictive analytics for demand forecasting
- Integration with additional communication platforms (Slack, WhatsApp)
- Multi-database support
- Fine-tuned domain-specific LLMs
- Advanced monitoring and governance for Responsible AI

---

## 11. Project Type

**Capstone Project (Mentored & Co-authored)**  
Generative AI | Agentic Systems | Enterprise NLP

---

## 12. Mentorship & Authorship

**Dr. Arun Singh Pundir**  
Assistant Professor, CSE  
Thapar Institute of Engineering & Technology  

---

## 13. Academic Reference

This project is based on the research paper:

> *Intelligent Retail Management: A Hybrid LLM and SQL Architecture*  
> (Under Review)
