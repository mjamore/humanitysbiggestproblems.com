# Remote MCP client onboarding

Research date: 2026-09-15

## Decision

Ship one public HTTPS **Streamable HTTP** MCP endpoint with standards-based OAuth. Do **not** promise that pasting a prompt or API key installs it. The supported onboarding action is an explicit install/add-server step, followed by browser OAuth; a starter prompt is useful only **after** connection.

The minimum defensible launch promise is:

1. **Claude:** supported through its Custom Connector settings flow.
2. **Codex:** supported through the ChatGPT desktop/IDE “Add server” UI or Codex CLI.
3. **ChatGPT:** supported as a public plugin after OpenAI review and publication. Before approval, describe the developer-mode URL flow as a technical preview, not normal consumer onboarding.

Do not promise other clients at launch. Publish the standards-compliant MCP URL for experimentation, but label untested clients “not officially supported.”

## Verified support matrix

| Client/surface | Remote HTTP MCP | Browser OAuth / client registration | Can a pasted prompt add it? | Required setup | Authenticated-tool constraints |
|---|---|---|---|---|---|
| **ChatGPT web/desktop — published plugin** | Yes. A plugin can bundle remote MCP tools; ChatGPT and Codex share the public plugin catalog. | Yes. OpenAI documents OAuth 2.1 authorization code + PKCE, with CIMD, DCR, or a predefined client. Authentication may occur during install or first use. | **No documented portable mechanism.** Official instructions require selecting install in the Plugins Directory; prompts use an already-installed plugin. | Find plugin, select `+`, connect/sign in when prompted, then start a new chat. Publication requires OpenAI review. | Per-tool `noauth` or `oauth2`; server must validate token, audience, expiry, and scopes on every call. Developer mode exposes write tools. Destructive actions need human confirmation; annotations do not replace server-side authorization. |
| **ChatGPT — unpublished/custom server** | Yes, through developer mode using a public HTTPS `/mcp` endpoint. | Yes, using the same OAuth discovery/PKCE machinery. | **No.** Official flow is Settings + Plugins UI, not a chat prompt. | Enable Developer mode (availability depends on account/workspace policy), add the MCP URL, review discovered tools, and add the connection to a conversation. No manual JSON is required. | Full MCP access can include writes. Treat this as developer testing, not the nontechnical launch path. |
| **Codex local host — ChatGPT desktop app, CLI, IDE extension** | Yes. Streamable HTTP is supported. | Yes. OAuth, CIMD, and DCR are explicitly supported; browser sign-in begins from `Authenticate` or `codex mcp login`. | **No documented setup-by-prompt mechanism.** | Desktop/IDE: Settings → MCP servers → Add server → Streamable HTTP → URL → save/restart → Authenticate. CLI is an alternative. `config.toml` is available but **not required**. | Server/tool allowlists and approval modes are configurable. `writes` mode prompts for tools not marked read-only; server-side role and scope checks remain required. |
| **Claude, Claude Desktop, Cowork — custom connector** | Yes. Streamable HTTP is supported; legacy HTTP+SSE is being deprecated. | Yes. OAuth DCR and CIMD are supported out of the box, with S256 PKCE. Optional pre-registered client credentials are supported. | **No documented setup-by-prompt mechanism.** | Individual plans: Settings/Customize → Connectors → Add custom connector → paste URL → Add → Connect/sign in. Team/Enterprise owners must first add it for the organization. No manual JSON is required. | Claude does not support user-pasted bearer tokens or API keys in the connector URL. Users approve tools and may choose “Allow always”; tools must correctly declare read-only/destructive hints, and the server must enforce permissions. |

### Primary evidence

- OpenAI’s [Codex MCP documentation](https://learn.chatgpt.com/docs/extend/mcp) documents Streamable HTTP, OAuth/CIMD/DCR, the GUI and CLI setup paths, shared local configuration, and approval modes.
- OpenAI’s [plugin install documentation](https://learn.chatgpt.com/docs/plugins) documents directory installation, connection/authentication prompts, and the shared ChatGPT/Codex public catalog. [Publication requires review](https://developers.openai.com/plugins/deploy/submission).
- OpenAI’s [ChatGPT developer-mode connection flow](https://developers.openai.com/plugins/deploy/connect-chatgpt) requires a public HTTPS `/mcp` endpoint and explicit UI setup; availability can depend on account and workspace policy.
- OpenAI’s [authentication reference](https://developers.openai.com/plugins/build/auth) documents OAuth 2.1, PKCE, CIMD, DCR, discovery metadata, and per-tool auth schemes. Its [security guidance](https://developers.openai.com/plugins/guides/security-privacy) requires least privilege, scope enforcement, and confirmation for destructive actions.
- Anthropic’s [connector transport reference](https://claude.com/docs/connectors/building) documents Streamable HTTP, DCR, callback behavior, and protocol limits. Its [authentication reference](https://claude.com/docs/connectors/building/authentication) documents DCR/CIMD, S256 PKCE, and the prohibition on pasted bearer tokens or query-string credentials.
- Anthropic’s [custom connector setup](https://support.claude.com/en/articles/11175166-get-started-with-custom-connectors-using-remote-mcp) and [tool-action guidance](https://claude.com/docs/connectors/custom/remote-mcp) document the manual settings flow, organization-owner boundary, OAuth consent, and tool approvals.

## Server and auth contract

Build once for all three clients:

- Canonical endpoint: `https://humanitysbiggestproblems.com/mcp` over Streamable HTTP.
- Public HTTPS; no redirects to another origin.
- OAuth protected-resource metadata plus authorization-server discovery.
- Authorization-code flow with S256 PKCE.
- Support at least one automatic registration path. Both clients document **DCR and CIMD**; OpenAI prefers CIMD when available. Use whichever the chosen authorization system supports correctly, and do not implement both for launch unless interoperability testing or directory review requires it.
- Never place API keys/tokens in prompts, copied URLs, tool arguments, or tool results.
- Allow genuinely public read tools without authentication where safe. Challenge protected calls with `401` and `WWW-Authenticate`; this enables browser connection when a user first invokes a protected tool.
- Use narrow scopes and enforce them server-side. A minimal shape is public reads plus authenticated `vote`, `contribute`, and role-gated `review`/`admin`; exact scope names remain a product/security design decision.
- Separate read and write tools and set truthful `readOnlyHint` / `destructiveHint` annotations. Require platform authorization regardless of any client-side approval.

## Truthful onboarding copy

### Before OpenAI plugin approval

> **Connect your AI agent**
>
> Choose your agent below. You’ll add Humanity’s Biggest Problems once, then sign in securely in your browser. Never paste your API key into a chat.

- **Claude:** “Open Connectors, add our MCP URL, then sign in.”
- **Codex:** “Open MCP servers, add our Streamable HTTP URL, then authenticate.”
- **ChatGPT:** “Early-access setup requires Developer mode and may not be available for every account or workspace.”

### After OpenAI plugin approval

> **Connect ChatGPT or Codex**
>
> Install the Humanity’s Biggest Problems plugin, then sign in when prompted.

After connection, provide a separate starter prompt, clearly labeled **Start working** rather than **Set up**:

> Use Humanity’s Biggest Problems to show me the highest-priority open problems and help me choose one contribution direction.

## Claims to avoid

- “Paste this one prompt to install the MCP server.”
- “Works with every AI agent.”
- “Paste your API key into ChatGPT/Claude/Codex.”
- “No setup required” before a directory install and OAuth consent exist.
- “ChatGPT support” without qualifying developer-mode access while plugin review is pending.

## Launch acceptance checks

- Test the same endpoint and OAuth flow in Claude custom connectors, Codex desktop, Codex CLI, Codex IDE, ChatGPT developer mode, and the published OpenAI plugin when approved.
- Verify public read, first protected call, consent, token refresh, revoked access, insufficient scope, role denial, and logout/disconnect.
- Verify every write tool is correctly annotated and rejected server-side when the user lacks permission.
- Keep client-specific setup instructions versioned and timestamped; these surfaces and policies change independently.
