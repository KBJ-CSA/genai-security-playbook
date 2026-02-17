# LLM Attack Taxonomy

```mermaid
flowchart LR

A[LLM Attack Surface]

%% Categories
A --> B[Prompt Attacks]
A --> C[Context Attacks]
A --> D[Retrieval Attacks]
A --> E[System Attacks]
A --> F[Output Risks]

%% Prompt
B --> B1[Prompt Injection]
B --> B2[Jailbreaks]
B --> B3[Instruction Override]
B --> B4[Roleplay Exploits]

%% Context
C --> C1[Memory Poisoning]
C --> C2[Context Pollution]
C --> C3[Indirect Injection]
C --> C4[Conversation Drift]

%% Retrieval
D --> D1[RAG Poisoning]
D --> D2[Vector DB Manipulation]
D --> D3[Document Injection]
D --> D4[Provenance Spoofing]

%% System
E --> E1[Tool Exploitation]
E --> E2[Agent Chain Attacks]
E --> E3[Plugin Injection]
E --> E4[Privilege Escalation]

%% Output
F --> F1[Hallucinations]
F --> F2[Policy Misrepresentation]
F --> F3[Harmful Content]
F --> F4[Data Leakage]

%% Styling
classDef prompt fill:#FFE6E6,stroke:#CC0000,color:#000;
classDef context fill:#E6F0FF,stroke:#1A73E8,color:#000;
classDef retrieval fill:#E6FFE6,stroke:#188038,color:#000;
classDef system fill:#FFF4E6,stroke:#FB8C00,color:#000;
classDef output fill:#F3E6FF,stroke:#9334E6,color:#000;

class B,B1,B2,B3,B4 prompt;
class C,C1,C2,C3,C4 context;
class D,D1,D2,D3,D4 retrieval;
class E,E1,E2,E3,E4 system;
class F,F1,F2,F3,F4 output;
