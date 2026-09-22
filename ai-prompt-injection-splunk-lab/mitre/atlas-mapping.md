# MITRE ATLAS Mapping

This lab concerns AI-specific attack behaviors and should be mapped against the current MITRE ATLAS knowledge base when the repository is finalized.

Relevant technique concepts include:

- LLM Prompt Injection
- RAG Poisoning
- AI Agent Tool Invocation
- Exfiltration via AI Agent Tool Invocation

The exact technique IDs should be verified against the current ATLAS matrix before publication because ATLAS is a living knowledge base and technique identifiers/names can change between versions.

Reference:
https://atlas.mitre.org/

## Mapping Rationale

### Indirect Prompt Injection / RAG Poisoning

The malicious instruction was stored in a retrieved knowledge-base document rather than supplied directly by the user.

### AI Agent Tool Invocation

The injected instruction caused the agent to invoke tools that crossed security boundaries.

### Exfiltration via AI Agent Tool Invocation

The successful chain involved reading local content and attempting to transfer it through an external web request.

This mapping describes the simulated lab behavior; it does not claim that every tool call or RAG retrieval is malicious.
