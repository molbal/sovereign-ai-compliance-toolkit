# INFERENCE EVENT LOG SCHEMA
## Version: 1.0

### MANDATORY FIELDS (every record)
* **schema_version**: Log schema version for forward compatibility
* **timestamp_utc**: ISO 8601 timestamp in UTC; no local time offsets
* **correlation_id**: UUID generated at request ingress; links all events within a single execution cycle
* **session_id**: Identifier for the user or agent session
* **event_type**: inference_request / inference_response / tool_call_proposed / tool_call_validated / tool_call_executed / policy_gate_blocked / human_oversight_triggered / routing_decision / budget_limit_reached
* **service_name**: Identifier of the service emitting the log
* **model_id**: Model identifier as deployed
* **model_version**: Exact version or commit hash of the weight file
* **deployment_region**: Physical region of the inference node
* **data_sensitivity**: public / internal / confidential / restricted

### REQUEST FIELDS (inference_request events)
* **input_token_count**: Token count of the full prompt as submitted
* **routing_backend**: Which inference backend received the request
* **prompt_hash**: SHA-256 of the prompt content; full content only logged where sensitivity tier and policy explicitly permit it

### RESPONSE FIELDS (inference_response events)
* **output_token_count**: Token count of the generated response
* **latency_ms**: Time from request receipt to response emission
* **finish_reason**: stop / length / tool_call / content_filter / error; relevant for demonstrating content policy controls were active
* **response_hash**: SHA-256 of the response content

### TOOL CALL FIELDS (tool_call_* events)
* **tool_name**: Name of the tool or API targeted
* **proposed_payload**: Payload as drafted by the model before policy validation
* **validated_payload**: Payload after policy gate; difference between proposed and validated is the audit evidence that the gate functioned
* **execution_result**: Outcome code and summary returned by the tool

### POLICY AND OVERSIGHT FIELDS
* **gate_triggered**: schema_check / rbac_check / human_approval / budget_cap
* **gate_outcome**: passed / blocked / escalated
* **block_reason**: Populated when gate_outcome is blocked
* **approver_id**: Populated when human_oversight_triggered; cryptographic signature reference where applicable

### RETENTION AND ACCESS CONTROL NOTE
Log records containing personal data in prompt or response fields are regulated data objects. Apply the same retention limits, deletion enforcement, and access controls as the source data. The sensitivity field in each record is the signal that drives automated retention policy. If it is not populated correctly at emission time, the policy cannot function correctly at deletion time. Fix it at the source.
