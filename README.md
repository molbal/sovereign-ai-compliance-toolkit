# Sovereign AI Compliance Toolkit

Architectural intent without documentation fails as a compliance posture. A regulator conducting a conformity assessment under the EU AI Act, a DORA supervisory audit, or a GDPR enforcement inquiry will demand concrete records. They will ask for logs, registers, impact assessments, and conformity matrices. The gap between organizations that survive these reviews and those that fail rarely comes down to system quality. The difference usually comes down to paperwork, specifically the absence of structured artifacts that prove the system behaves exactly as the architecture claims.

The checklists and templates in this repository serve as starting points rather than finish lines. You must adapt them to your sector, your regulator, and your specific deployment topology. A financial entity subject to DORA will weight the asset register entries differently than a healthcare provider whose primary exposure falls under the Medical Device Regulation. The structure remains identical across these domains, though the risk calculus changes entirely.

## Repository Contents

### EU AI Act Conformance Matrix
A framework for classifying high-risk AI systems (Annex III) and documenting technical parameters, data governance, logging capabilities, human oversight, and transparency requirements.

### DORA ICT Asset Register
A tracking template for financial entities to maintain a complete and current register of all contractual arrangements with ICT third-party service providers, specifically mapped for AI infrastructure dependency chains.

### Inference Event Log Schema
A structured logging architecture designed for proxy-layer implementation. It provides an immutable record of system processing, model versions, and outcomes to satisfy both operational diagnostics and regulatory audits.

### GDPR Inference Data Checklist
A comprehensive review framework for lawful basis documentation, data minimization in prompt design, physical residency verification, data subject rights handling, and security controls for inference workloads.

## Companion Book: Beyond the Public Cloud

This toolkit serves as the official companion repository to the book **[Beyond the Public Cloud](https://www.amazon.com/dp/B0GWRG9ZBM?nsdOptOutParam=true)**.

The public cloud promised simplicity. It delivered convenience, then invoices, then a compliance officer asking questions nobody had prepared answers for.

*Beyond the Public Cloud* is a practical guide for solution architects, CTOs, and technical leads who have moved past the proof-of-concept stage and are now responsible for the next phase. It covers the architecture of private, sovereign AI infrastructure for organizations operating under European law: what it actually requires, what it genuinely costs, and where the gap between vendor assurances and regulatory defensibility tends to be widest.

Rather than treating the public cloud as an adversary, the book illustrates that mindlessly outsourcing core inference to unaccountable external endpoints creates compounding consequences that eventually become expensive to explain. It treats the EU AI Act, GDPR, and DORA as the stable legal environment that serious infrastructure is designed to operate within.

Topics covered include the anatomy of a sovereign inference stack, the economics of self-hosted versus API deployment at scale, data residency as a physical and legal fact rather than a configuration flag, small language models at the edge, agentic workflow design with a compliant control plane, and the physical security risks that most zero-trust frameworks were not designed to address.

The hype cycle will continue with or without your participation. This book is for the people responsible for building systems that still work when the cycle ends.
