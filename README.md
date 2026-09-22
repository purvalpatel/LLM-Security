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
- Red Team
- Penetration Test
- Bug Bounty
- Conformity Assessment

# Risk Management & Threat Modeling
### - Risk Management Programs:
- NIST AI RMF ( Risk Management Factor )
    - Govern
    - Map
    - Measure
    - Manage
- MITRE ATLAS
Tactics: <br>
    - Reconnaissance
    - Resource Development
    - Initial Access
    - ML Model Access
    - Execution
    - Persistance
    - Defence Evasion
    - Credential Access
    - Discovery
    - Collection
    - ML Attack Staging
    - Exfilteration
    - Impact

### Threat Modeling AI system with Adapted STRIDE
STRIDE (Spoofing, Temparing, Repudiation, Information Disclosure, DOS, Elevation of privillege)
For AI systems:
- Temparing
- Information Disclosure
- Denial of service
- Elevation of privillege

### The Governance Artifacts every program needs
- AI Risk Register
- Model Card
- Residual risk Acceptance

# AI Governance & Complaince
- EU-AI Act
- GDPR
- HIPPA in LLM Context
- ISO/IEC 42001
- CCPA

### Governance Artifacts you will actually be asked to produce:
- AUP (Acceptable use policy)
- Conformity assessment
- Data Protection impact Assessment (DPIA)

# Blue Team Defense & Monitoring
- Defence in depth for LLM applications
    - Input Filter
    - Output Limiter
    - Rate Limiter
    - Observability/SIEM
- Detection
    - Behavioural Baselining
    - Static Signatures
- Canary Tokens And Honey Tokens
- Logging
- Observability
- PII Redaction
- AI Specific Incident Response
    - Contain
    - Preserve
    - Assess
    - Remediate
    - Notify
- Purple Teaming - read team + Blue team


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
- Sandboxing
- Circuit Breakers
- Tool Allow-listing & Schema Validation
- System Prompt/Instruction-data channel isolation
- Multi-Agent Trust boundaries
- MCP security Architecture
- Secure RAG pipelines design

# Agent Lifecycle & Operations
- Drift Monitoring
- Regression Testing
- Canary Rollout
- Continuous Automated red teaming
- Secure Decommisioning
- Vibe-coding risk in AI-Assisted development

# AIML Supply chain & Third Party risk
- Model Provenance & Unsafe Deserialization
- Unsafe deserialization
- AI-BOM / ML-BOM
- Plugin/MCP marketplace vetting
- Rug-pull attacks
