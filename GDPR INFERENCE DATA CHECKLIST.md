# GDPR INFERENCE DATA CHECKLIST
## Version: 1.0 | Review cadence: per deployment and quarterly

### LAWFUL BASIS AND PURPOSE LIMITATION
- [ ] A lawful basis under Article 6 is identified and documented for each inference workload processing personal data
- [ ] The purpose for which data is processed during inference does not exceed the purpose for which it was originally collected
- [ ] Special category data under Article 9 has been identified, and an explicit consent record or Article 9(2) exemption is documented where applicable

### DATA MINIMISATION AND PROMPT DESIGN
- [ ] System prompts have been reviewed to confirm personal data is injected only where strictly necessary for the task
- [ ] Retrieved context is scoped to the minimum required; full-document injection into the context window is reviewed and justified where used
- [ ] Conversation history injected into context is subject to a documented retention limit before truncation
- [ ] Output token volume has been reviewed; verbose generation containing personal data that is not required by the task has been constrained at the prompt or schema level

### RESIDENCY AND TRANSFER CONTROLS
- [ ] The physical location of all inference hardware is confirmed and documented for each workload tier
- [ ] Every dependency in the inference stack (model registry, secrets management, logging pipeline, vector store) is mapped and verified to be within the residency boundary or confirmed as non-contact with personal data
- [ ] No automated failover path routes personal data outside the defined residency boundary; this has been tested under simulated failure conditions, not just reviewed on a diagram
- [ ] If a third-party processor is involved, a compliant Article 28 Data Processing Agreement is in place and the processor's sub-processor list has been reviewed

### DATA SUBJECT RIGHTS
- [ ] A documented procedure exists for responding to subject access requests that may implicate data processed during inference
- [ ] A deletion procedure exists for personal data that may be represented in fine-tuned model weights, including a documented position on whether weight retraining is required to satisfy an erasure request
- [ ] Retention periods for inference logs containing personal data are defined, enforced by automated deletion, and documented

### SECURITY CONTROLS (ARTICLES 5 AND 32)
- [ ] KV cache isolation between tenant sessions has been explicitly configured and verified; inference engine defaults have not been assumed to be sufficient
- [ ] Inference logs containing prompt and response content are classified at the sensitivity level of the data they may contain and subject to equivalent access controls
- [ ] A prompt injection risk assessment has been completed for any workload that retrieves content from external or user-controlled sources before injecting it into the context window
- [ ] Weight files for models fine-tuned on personal data are stored with access controls and audit logging equivalent to the source data

### INCIDENT RESPONSE
- [ ] A documented procedure exists for detecting and responding to inference-layer data incidents, covering KV cache leakage, prompt injection exploitation, and model weight exfiltration
- [ ] The 72-hour breach notification requirement under Article 33 has been mapped to the actual detection latency of the inference monitoring pipeline, not assumed to be satisfiable in the abstract
