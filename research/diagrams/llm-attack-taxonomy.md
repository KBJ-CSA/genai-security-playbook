# LLM Attack Taxonomy

```mermaid
flowchart TD

A[LLM Attack Surface]

A --> B[Prompt-Level Attacks]
A --> C[Context & Memory Attacks]
A --> D[Knowledge & Retrieval Attacks]
A --> E[System & Integration Attacks]
A --> F[Output & Abuse Risks]

%% Prompt Attacks
B --> B1[Direct Prompt Injection]
B --> B2[Jailbreaks]
B --> B3[Instruction Override]
B --> B4[Roleplay Exploits]

%% Context Attacks
C --> C1[Session Memory Poisoning]
C --> C2[Context Pollution]
C --> C3[Conversation Drift]
C --> C4[Indirect Prompt Injection]

%% Retrieval Attacks
D --> D1[RAG Poisoning]
D --> D2[Vector DB Manipulation]
D --> D3[Document Injection]
D --> D4[Data Provenance Spoofing]

%% System Attacks
E --> E1[Tool Exploitation]
E --> E2[Agent Chain Manipulation]
E --> E3[Plugin Injection]
E --> E4[Permission Escalation]

%% Output Risks
F --> F1[Hallucinated Facts]
F --> F2[Policy Misrepresentation]
F --> F3[Harmful Content Generation]
F --> F4[Confidential Data Leakage]
