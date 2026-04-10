# EU AI ACT CONFORMANCE MATRIX
## Version: 1.0 | Applies to: High-Risk AI Systems (Annex III)

### SYSTEM CLASSIFICATION
- [ ] The system has been assessed against Annex III use case categories
- [ ] A documented classification decision exists, including the reasoning for the risk tier assigned

### TECHNICAL DOCUMENTATION (ARTICLE 11)
- [ ] A technical documentation package covers system architecture, training data characteristics, and intended purpose
- [ ] The model version in production is recorded with the deployment date and the validation results at that version
- [ ] Third-party components, including open-weight models, inference engines, and retrieval systems, are identified with version, license, and provenance documentation
- [ ] Performance is documented on the actual task the system is deployed for, separately from generic benchmark results

### DATA GOVERNANCE (ARTICLE 10)
- [ ] Training and fine-tuning datasets are documented with provenance, known limitations, and data preparation steps
- [ ] Validation and test datasets are documented and kept separate from training data
- [ ] A bias assessment has been conducted and findings are documented, including any mitigations applied

### LOGGING AND AUDITABILITY (ARTICLE 12)
- [ ] The system generates logs sufficient to reconstruct system operation post-hoc for the retention period required by the applicable sector regulation
- [ ] Logs are stored in a write-once or cryptographically tamper-evident format
- [ ] Log retention period is defined and enforced
- [ ] A documented procedure exists for retrieving logs in response to a regulatory request within an operationally realistic timeframe

### HUMAN OVERSIGHT (ARTICLE 14)
- [ ] A named natural person is designated as responsible for oversight of each high-risk system in production
- [ ] That person has documented understanding of the system's capabilities, limitations, and known failure modes
- [ ] Intervention procedures are documented and tested: the oversight person can halt or override system outputs without requiring engineering involvement for standard scenarios
- [ ] High-risk automated decisions are subject to a human review gate before producing legal or similarly significant effects on individuals

### TRANSPARENCY AND USER INFORMATION (ARTICLE 13)
- [ ] Users are informed they are engaging with an AI system where this is not self-evident from context
- [ ] The system's intended purpose, performance characteristics, and known limitations are documented in a form accessible to users or their representatives
- [ ] Instructions for use are versioned alongside the model version they describe, so the documentation and the system cannot drift apart
