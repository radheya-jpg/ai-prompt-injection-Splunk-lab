# Sigma Detection

`ai-agent-exfiltration.yml` contains a lab-specific behavioral Sigma rule for sessions where an AI agent invokes both `file_read` and `web_fetch`.

The Splunk implementation correlates the two tool calls by `session_id`.

The rule should be treated as a starting point. Production deployments should add organization-specific allowlists, tool identities, data sensitivity context, and successful/failed tool-call state where available.
