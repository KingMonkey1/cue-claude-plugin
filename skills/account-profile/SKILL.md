---
name: account-profile
description: Use Cue when the user asks which Cue account, email, profile, subscription, entitlement, Free/Pro status, or plan is connected.
---

# Cue account profile

For any question about the connected Cue account, email address, profile, subscription, entitlement, Free/Pro status, or plan, call the Cue MCP tool `get_profile` before answering.

Do not infer or guess account identity from Claude, chat history, or prior messages. The `get_profile` result is the source of truth.

Return the connected email and plan concisely.

If authentication is required, tell the user to connect or reconnect Cue. If the server is unavailable, say that Cue account lookup is temporarily unavailable.
