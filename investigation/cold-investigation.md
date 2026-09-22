# Cold Investigation

The investigation was performed after the experiment rather than by following the attack live.

## Initial Search

The Splunk dataset contained agent telemetry under:

`source="http:llm-agent"`

with:

`sourcetype=llm_agent_logs`

The telemetry included fields such as:

- `session_id`
- `event_type`
- `tool`
- `argument`
- `result`
- `prompt`
- `response`

## Reconstruction

The successful session was reconstructed by following the same `session_id` across event types.

The relevant sequence was:

1. `user_query`
2. `retrieval`
3. `model_prompt`
4. `tool_call_attempted` for `file_read`
5. `tool_call_result`
6. `tool_call_attempted` for `web_fetch`
7. external test endpoint activity confirming the exfiltration attempt

The `model_prompt` event was especially useful because it showed the poisoned document entering the model context.

## Investigation Goal

The goal was not simply to find the word "prompt injection". It was to determine whether the agent actually crossed a meaningful tool boundary and whether the attempted exfiltration succeeded.
