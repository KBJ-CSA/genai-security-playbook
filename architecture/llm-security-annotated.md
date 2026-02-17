# LLM Security Architecture — Annotated with MAESTRO Mapping

This document combines:

- Reference architecture  
- Trust boundaries  
- Attack path overlays  
- MAESTRO control mapping  

---

| Architecture Component         | MAESTRO Category | Risk Addressed                    |
| ------------------------------ | ---------------- | --------------------------------- |
| API Gateway / WAF              | Resilience       | Traffic abuse, bot attacks        |
| Authentication & Authorization | Access           | Unauthorized data access          |
| Prompt Firewall                | Manipulation     | Prompt injection, jailbreaks      |
| Retrieval Access Control       | Access           | Sensitive document exposure       |
| Document Sanitization          | Supply Chain     | RAG poisoning                     |
| Tool Permission Scoping        | Execution        | Unauthorized actions              |
| Output Risk Filter             | Trust            | Hallucinations, misrepresentation |
| Logging & SIEM                 | Oversight        | Undetected attacks                |
| Rate Limiting                  | Resilience       | Prompt flooding                   |
| Human Approval Gates           | Execution        | High-risk automation              |

---

## 🛡️ Annotated Architecture Diagram

```mermaid
flowchart LR

subgraph Z1[External User Zone]
U[End User]
end

subgraph Z2[Perimeter Security Zone]
GW[API Gateway / WAF]
end

subgraph Z3[Application Trust Zone]
APP[Application Backend]
RAG[Retrieval Service]
end

subgraph Z4[AI Processing Zone]
PF[Prompt Firewall]
LLM[LLM Provider]
OR[Output Risk Filter]
end

subgraph Z5[Data Trust Zone]
VDB[(Vector Database)]
DOC[Document Store]
end

subgraph Z6[External Services Zone]
TOOLS[External Tools / APIs]
end

subgraph Z7[Monitoring & Governance Zone]
LOG[Logging]
SIEM[Security Analytics]
end

U --> GW --> APP
APP --> PF --> LLM
LLM --> OR --> APP

APP --> RAG --> VDB
RAG --> DOC

LLM --> TOOLS

APP --> LOG --> SIEM
PF --> LOG
OR --> LOG

U -. Prompt Injection .-> LLM
U -. Jailbreak Attempt .-> PF
DOC -. RAG Poisoning .-> LLM
VDB -. Data Exfiltration .-> APP
LLM -. Tool Abuse .-> TOOLS
LLM -. Hallucination Risk .-> APP

classDef user fill:#E3F2FD,stroke:#1E88E5,color:#000;
classDef edge fill:#E8F5E9,stroke:#2E7D32,color:#000;
classDef app fill:#FFF8E1,stroke:#F9A825,color:#000;
classDef ai fill:#F3E5F5,stroke:#8E24AA,color:#000;
classDef data fill:#E0F2F1,stroke:#00897B,color:#000;
classDef tools fill:#FBE9E7,stroke:#D84315,color:#000;
classDef monitor fill:#ECEFF1,stroke:#455A64,color:#000;

class U user;
class GW edge;
class APP,RAG app;
class PF,LLM,OR ai;
class VDB,DOC data;
class TOOLS tools;
class LOG,SIEM monitor;
