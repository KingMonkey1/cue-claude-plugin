# Cue connections — setup and acceptance checks

Updated 21 October 2026. These are connection instructions, not claims of platform approval or completed host testing.

## Common connection

- Name: Cue
- Server URL: `https://cue-mcp-production.up.railway.app/mcp`
- Transport: Streamable HTTP
- Authentication: OAuth; sign in to your Cue account on the Cue service's own page.
- Permissions: read your Cue account/email/plan and submit selected prompts for scoring and rewriting.
- Never paste a Cue password, browser session, backend token or Stripe key into a client configuration.
- Cue provides scores and suggested rewrites. It does not automatically send a prompt, guarantee factual accuracy, or train the host's underlying model.

## Free access and Cue Pro

GitHub and VS Code are discovery and connection channels; they do not process Cue payments. After connecting, sign in with the same Cue account used on the website. Cue applies the account's allowance on the hosted service: Free users receive the currently advertised free improvements, while Cue Pro provides expanded access. When the Free allowance is reached, use **https://cue-prompt.com/pro** to review Cue Pro and upgrade securely through Cue's checkout. Cue's MCP tools never take payment or change a subscription, and no card details belong in an MCP or VS Code configuration.

## Lovable

Open Connectors, select +, choose MCP server. Name it Cue, use the URL above, keep direct connection, choose OAuth and Add & authorize. Sign in to Cue and return to Lovable. Custom chat connectors are personal to the connecting user; they do not automatically ship in a published Lovable app.

Source: https://docs.lovable.dev/integrations/custom-mcp

## Cursor

Add the entry from cursor-mcp.json to your existing MCP configuration, preserving other servers. Use the MCP settings to connect/authenticate Cue. Current Cursor documentation lists a desktop loopback callback and a separate web callback; both are supported through exact registered redirects. No separate Cursor listing has been approved.

Source: https://cursor.com/docs/mcp

## VS Code / GitHub Copilot

Run MCP: Add Server, select HTTP, enter the server URL and name Cue. Choose the intended user or workspace scope. The equivalent file format is vscode-mcp.json. Start the server and complete OAuth when requested. Use Agent mode with Cue tools enabled. Preserve any other existing server entries.

Source: https://code.visualstudio.com/docs/agent-customization/mcp-servers

## Replit

Open Integrations and the MCP servers section for Replit Agent. Add Cue and its remote URL, then Test & Save. Complete the OAuth flow. Replit's own security scanner or workspace policies may also govern tool access.

Source: https://docs.replit.com/pt/references/mcp/overview

## Emergent

Wingman documents remote HTTP/Streamable HTTP MCP integrations: supply Cue's server URL and use its authentication flow. The main builder's custom-agent and general MCP documentation describe different configuration surfaces; confirm the actual form before configuring it. Do not claim the main builder is tested or place a remote URL in a command-only field.

Sources: https://help.emergent.sh/custom-mcp-integrations and https://help.emergent.sh/custom-agents

## Run in each host before announcing support

1. Connect and sign in using a controlled Cue account. Confirm OAuth returns to the correct host and never exposes your Cue password.
2. Ask: "Which Cue account and plan am I connected to?" Confirm the host calls get_profile and reports the actual account.
3. Ask: "Use Cue to improve this prompt: Help me plan a small business website. Ask for my audience, goals and budget, then propose the pages and delivery steps." Confirm improve_prompt returns a score, feedback and rewrite.
4. Confirm the original prompt is not automatically sent or replaced without the user's instruction.
5. Test a controlled Free account through its remaining allowance; confirm the next attempt gets the actual limit response. Do not consume a real customer's quota for testing.
6. Test an authorised Pro account separately. Confirm entitlement is read from Cue, never granted by a client-supplied flag.
7. Disconnect/revoke and confirm reconnect is required when the session is invalid. Check refresh and sign-in again after restarting the host.

The local regression suite uses mocked backend/Redis fixtures. It verifies OAuth controls and limit-error handling, but does not prove a real user's billing entitlement or a host's final UI.

## Public listing versus connection

The official MCP Registry publishes metadata for the hosted service. It is a discovery channel, not a paid marketplace: users connect to Cue, then upgrade on Cue's website if they need expanded access. The registry does not publish Cue's private implementation or guarantee inclusion in Cursor, Lovable, Replit or other curated catalogues. Each platform's listing decision remains separate.
