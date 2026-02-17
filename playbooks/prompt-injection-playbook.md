# Prompt Injection Testing Playbook

## 1. Purpose

This playbook defines a structured methodology for identifying and validating prompt injection vulnerabilities in GenAI applications.

Goals:

- Identify unsafe instruction handling  
- Test data exfiltration paths  
- Evaluate guardrail effectiveness  
- Provide remediation guidance  

---

## 2. Scope

Applicable to:

- Chatbots  
- RAG systems  
- AI copilots  
- Agent workflows  

Components tested:

- User input handling  
- System prompts  
- Retrieval context  
- Tool invocation  
- Output filtering  

---

## 3. Threat Model

### Key Risks

- Instruction override  
- Sensitive data leakage  
- Unauthorized actions  
- Policy bypass  

### Trust Boundaries

User → Application  
Application → LLM  
LLM → Tools  
Retrieval Sources → Model  

---

## 4. Attack Categories

### Direct Prompt Injection
Attempts to override system instructions.

### Indirect Prompt Injection
Malicious instructions embedded in retrieved data.

### Data Exfiltration
Attempts to extract hidden or sensitive information.

### Tool Misuse
Manipulating the model into executing unintended actions.

---

## 5. Testing Methodology

1. Recon — Understand architecture  
2. Baseline — Capture normal behavior  
3. Attack — Execute payloads  
4. Validate — Confirm exploitability  
5. Document — Record evidence  

---

## 6. Evidence Collection

- Payloads used  
- Model responses  
- Screenshots/logs  
- Reproduction steps  

---

## 7. Risk Rating

| Severity | Criteria |
|----------|---------|
| Critical | Sensitive data exposure |
| High | Policy bypass or tool misuse |
| Medium | Partial instruction override |
| Low | Minor unexpected behavior |

---

## 8. Mitigations

### Preventive
- Input validation  
- Context isolation  
- Retrieval sanitization  
- Least-privilege tool access  

### Detective
- Prompt monitoring  
- Logging and alerting  

### Corrective
- Guardrail tuning  
- Output filtering  

---

## 9. Reporting

Each finding should include:

- Description  
- Payload  
- Impact  
- Evidence  
- Recommendation  

---

## 10. Lessons Learned

Track recurring patterns across assessments to improve testing coverage.

---
