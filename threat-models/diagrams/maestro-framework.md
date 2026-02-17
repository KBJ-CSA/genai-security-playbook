# MAESTRO Framework Diagram

```mermaid
flowchart LR

A[LLM System Risks]

A --> M[Manipulation]
A --> AC[Access]
A --> E[Execution]
A --> S[Supply Chain]
A --> T[Trust]
A --> R[Resilience]
A --> O[Oversight]

M --> M1[Prompt Injection]
M --> M2[Jailbreaks]
M --> M3[Context Poisoning]

AC --> AC1[Data Leakage]
AC --> AC2[Unauthorized Retrieval]

E --> E1[Tool Misuse]
E --> E2[Unauthorized Actions]

S --> S1[Poisoned Data]
S --> S2[Third-Party Risk]

T --> T1[Hallucinations]
T --> T2[Misrepresentation]

R --> R1[Prompt Flooding]
R --> R2[Service Degradation]

O --> O1[Logging Gaps]
O --> O2[Monitoring Failures]
