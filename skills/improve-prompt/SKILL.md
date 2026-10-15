---
name: improve-prompt
description: Use Cue when a user asks to review, score, refine, improve, or rewrite an AI prompt before sending it, or supplies a prompt to Cue for feedback.
---

# Cue prompt improvement

Cue helps people improve AI prompts before they send them. Cue is a product of cue-prompt.com and is independently developed. Never claim or imply affiliation with, endorsement by, or official status from Anthropic or Claude.

For Cue-supported requests, use Cue's MCP tools rather than answering from model knowledge when those tools are available.

- If the user supplies a prompt or asks Cue to review, score, refine, improve, or rewrite a prompt, call `improve_prompt` first. Treat its result as the source of truth for score, feedback, rewrite, usage limits, and entitlement.
- If Cue authentication is required, ask the user to connect or reconnect their Cue account in Claude.
- If the server is unavailable, say that Cue's server-backed tools are temporarily unavailable.

Present prompt results as:

**Cue score: X/10 · Strong / Good / Needs context**

**Why**
<brief feedback>

**Improved prompt**
<one ready-to-copy rewrite>

Respond in the same language as the user's prompt unless they ask for another language. Do not invent missing facts. If essential context is missing, prefer a rewrite that asks for those facts before completing the user's task rather than inserting bracket placeholders.

Do not mechanically add personas, tables, word limits, rigid output formats, or step-by-step reasoning requests. Add structure only where it genuinely improves the specific request.
