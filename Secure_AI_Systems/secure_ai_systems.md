Architectural Shift: Traditional vs. AI-Augmented Web Applications

1. system Architectural changes:
   - Traditional applications follow a predictable flow: User Interface → API → Database → Response.
   - Integrating AI introduces new processing layers and dynamic data paths that bypass standard security controls.

2. Core component Evolution
    - Input: Transitions from structured forms and API parameters to free-form natural language prompts.
    - Processing: Moves from deterministic code execution to probabilistic model inference.
    - Data Access: Shifts from direct database queries to model-mediated retrieval (e.g., RAG).
    - Output: Changes from template-rendered static responses to generated natural language text.
    - Dependencies: Expands beyond software libraries and frameworks to include pre-trained models and vector embeddings.

* It is harder to tract it, bc it is all based on statistic / probabilities 

most critical vulnerabilities in LLM applications:
1. Prompt Injection
2. Sensitive Information Disclosure: Leaking confidential data, PII, or system details through responses
3. Supply Chain: Compromised pre-trained models, datasets, and third-party dependencies introduced before deployment
4. Data and Model Poisoning:Corrupting training data or model weights to alter behaviour    
5. Improper Output Handling: 
6. Excessive Agency: AI components with more privilege or autonomy than necessary
7. System Prompt Leakage
8. Vector and Embedding Weaknesses: Exploiting retrieval mechanisms and embedding pipelines
9. Misinformation: LLM generating false or misleading content
10. Unbounded Consumption: Resource exhaustion, cost explosion, denial of service 

NIST; MITRE, & OWASP
* NIST is the building code & architectural blueprint (high-level risk management and policy).
* MITRE ATT&CK is the burglar's playbook (understanding how adversaries move and execute attacks).  documents how adversaries exploit them
* OWASP is the checklist for secure doors and windows (fixing specific application vulnerabilities). classifies what the vulnerabilities are
  >  OWASP names the vulnerabilities, and MITRE ATLAS describes how adversaries exploit them, the NIST AI RMF asks whether the organisation has a repeatable process for addressing them

owasp llm top 10: 
* system level Threats 
    1. llm10 > unbounded consumption: The main target is the AI service/API’s resources and budget, rather than trying to “break” the LLM itself.
        Defence: Rate limiting, input length validation, cost ceilings, and per-user quotas enforced at the API gateway.
    2. llm07 > System Prompt leakage: The llm reveals its hidden operating instructions to someone who should not have them
        Defence: Never put secrets, credentials, or internal URLs in a system prompt. Write prompts as if an attacker will eventually read them, because they might.
    3. llm05 > Improper Output Handling: Treating LLM Output as safe and passing it straight into other systems without checking it first
        Defence: Never trust LLM output as input to another system.
    4. llm06 > Excessive Agency: Giving an AI system more tools, permissions, or freedom to act than it actually needs.
        Defence: Least privilege for every AI component. Read-only by default. Scoped API tokens. Human approval is required before any write, delete, or deployment action.
    5. llm02 > sensitive information disclosure: The AI system leaking confidential information, ex_The AI system leaking confidential information 
        Defence: Strip PII from logs before storing them. Encrypt conversation data. Be deliberate about what you send to external model APIs.
        
difference for clarifying 
LLM07 = information leaks OUT 🔓
LLM05 = dangerous output goes IN somewhere else and gets executed 💻

