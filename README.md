# LLM Attacks and Adversarial Techniques
- **Direct**    →    Attack the prompt directly
- **Indirect**    →    Attack through external data
- **Training Time**    →    Attack while learning
- **Supply chain**    →    Attack something you depend on(Third Party)
- **Jailbreak Families** → Bypass model safety
    - PAIR
    - DAN Style
    - Skeleton Key
    - Crescendo
    - Many-Shot Jailbreaking
    - Adversarial Smuggling
- **Filter Evasion**  →  Hide the attack from detection
    - **Token Smuggling**  →   Encodes or splits sensitive words/instructions into tokens
    - **Homologlyphs**    →    Replaces normal characters with visually similar Unicode characters
- **Privacy and IP attacks** ( 4 ways to steal from model )
    - **Model Extraction**     → Steal model behavior
    - **Membership Inference**    → Was my data in training?
    - **Model Invension**    → Reconstruct sensitive information
    - **Property inference**   → Discover dataset properties
- **Availability Attacks**   → Make inference expensive/unavailable
- **Data and Model Poisioning** → Corrupt training/model integrity

# OWSAP Top 10 For LLM Applications & Red Teaming
- LLM01  :  Prompt Injection        → INPUT
- LLM02  :  Sensitive information disclosure    →    DATA
- LLM03  :  Supply chain    →   DEPENDENCY 
- LLM04  :  Data and Model poisioning    →    TRAINING    
- LLM05  :  Improper Output Handling    →       OUTPUT
- LLM06  :  Excessive Agency    →    PERMISSION
- LLM07  :  System Prompt Leakage    →       PROMPT
- LLM08  :  Vector & Embedding weakness    →       RAG
- LLM09  :  Misinformation    →       ANSWER
- LLM10  :  Unbound consumption    →       RESOURCES

### Some other terms:
- Red Team          → Simulate attacker
- Pen Test          → Exploit vulnerabilities
- Bug Bounty        → Find bugs → Get reward
- Conformity        → Check against standards

# Risk Management & Threat Modeling
### - Risk Management Programs:
- **NIST AI RMF** ( Risk Management Factor ) → How an organization MANAGES AI RISK
    - Govern
    - Map
    - Measure
    - Manage
- **MITRE ATLAS** → How an ATTACKER attacks an AI system <br>
Tactics: MITRE ATLAS (Adversarial Threat Landscape for Artificial-Intelligence Systems) is a knowledge base of adversary tactics and techniques targeting AI-enabled systems. <br>

| Tactic                   | One-line explanation                                                                                                                          |
| ------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------- |
| **Reconnaissance**       | Attacker gathers information about the target AI system, models, infrastructure, users, or defenses.                                          |
| **Resource Development** | Attacker obtains or creates resources such as accounts, infrastructure, datasets, tools, or models needed for an attack.                      |
| **Initial Access**       | Attacker obtains an initial foothold or access to the target AI environment.                                                                  |
| **AI/ML Model Access**   | Attacker gains access to an AI model or its interfaces to interact with, manipulate, or attack it.                                            |
| **Execution**            | Attacker executes malicious code, commands, prompts, or actions within the target environment.                                                |
| **Persistence**          | Attacker maintains access to the AI system or environment after the initial compromise.                                                       |
| **Defense Evasion**      | Attacker attempts to hide malicious activity or bypass security controls and detection mechanisms.                                            |
| **Credential Access**    | Attacker attempts to obtain passwords, API keys, tokens, or other authentication credentials.                                                 |
| **Discovery**            | Attacker identifies systems, models, data, configurations, services, or other resources available in the environment.                         |
| **Collection**           | Attacker gathers valuable data, prompts, model information, training data, or other target information.                                       |
| **ML Attack Staging**    | Attacker prepares or positions malicious inputs, data, models, or other components for an ML-focused attack.                                  |
| **Exfiltration**         | Attacker transfers stolen data, model information, credentials, or other valuable information outside the target environment.                 |
| **Impact**               | Attacker causes harmful consequences such as data manipulation, service disruption, model degradation, financial loss, or unsafe AI behavior. |


### Threat Modeling AI system with Adapted STRIDE
**STRIDE** (Spoofing, Temparing, Repudiation, Information Disclosure, DOS, Elevation of privillege)
For AI systems:
- **Temparing**    → Change something      → Integrity
- **Information Disclosure**  → See something        → Confidentiality
- **Denial of service** → Stop something        → Availability
- **Elevation of privillege** → Gain more access     → Authorization

### The Governance Artifacts every program needs
- **AI Risk Register** → What risks do we have?
- **Model Card**  → What is this model and what are its limitations?
- **Residual risk Acceptance** → What risk remains, and who accepts it?

# AI Governance & Complaince
- EU-AI Act  →      AI RISKS
- GDPR →           PERSONAL DATA
- HIPPA in LLM Context →          HEALTH DATA / PHI
- ISO/IEC 42001 →      AI GOVERNANCE
- CCPA →           CALIFORNIA PRIVACY

### Governance Artifacts you will actually be asked to produce:
- AUP (Acceptable use policy)   → What CAN users do?
- Conformity assessment → Does the AI MEET requirements?
- Data Protection impact Assessment (DPIA) → What PRIVACY risks exist?

# Blue Team Defense & Monitoring
```
BLUE TEAM
   ↓
Prevent → Detect → Monitor → Respond
```

- Defence in-depth for LLM applications (PREVENT)
    - Input Filter
    - Output Limiter
    - Rate Limiter
    - Observability/SIEM
- DETECTION
    - Behavioural Baselining
    - Static Signatures
    - Canary Tokens And Honey Tokens
- MONITOR
    - Logging
    - Observability
    - PII Redaction

- RESPOND : AI Specific Incident Response
    - Contain
    - Preserve
    - Assess
    - Remediate
    - Notify
 
### PURPLE TEAM
```
Red Team + Blue Team
Attack → Detect → Learn → Improve
```

# Identity & Access Management for AI
- RBAC/ABAC/Zero Trust
- Secure Accounts
- Capability Tokens
- Delegated Authorization
    - OAuth 2.0
    - OIDC
- Secret Management
- Vector Database Access Control
- Human-in-the-loop Authorization gates

# Secure Agent Architecture & Design
- Anatomy of secure Agents tool pipeline
- Sandboxing   →      Runs agent code and tools in an isolated environment with restricted filesystem.
- Circuit Breakers    →     Automatically stop or pause agent/tool execution when abnormal behavior occured.
- Tool Allow-listing & Schema Validation    →     Allow only approved tools and validate every tool parameter against a strict schema before execution.
- System Prompt/Instruction-data channel isolation
- Multi-Agent Trust boundaries
- MCP security Architecture
- Secure RAG pipelines design

# Agent Lifecycle & Operations
- **Drift Monitoring**        → Is behavior changing?
- **Regression Testing**     → Did the change break something?
- **Canary Rollout**     → Test on a small percentage first
- **Continuous Automated red teaming**    → Continuously attack/test it
- **Secure Decommisioning**     → Remove access safely
- **Vibe-coding risk in AI-Assisted development**    → Don't blindly trust AI-generated code

# AIML Supply chain & Third Party risk
- **Model Provenance & Unsafe Deserialization**    →    From where the AI model come from.
- **Unsafe deserialization** → Loading untrusted serialized objects/models can allow attackers to execute arbitrary code on the system.
- AI-BOM / ML-BOM → An inventory of AI/ML models, datasets, libraries, dependencies, and components used in an AI system.
- Plugin/MCP marketplace vetting → Assess and verify third-party AI plugins/MCP servers
- Rug-pull attacks  →  A trusted AI component is initially safe but later updated or replaced with malicious code after users adopt it.
