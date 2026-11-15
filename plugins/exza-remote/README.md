# EXZA Remote for Claude Code (RC50)

**GitHub Marketplace installation:**

~~~bash
claude plugin marketplace add exzade/EXZA-Remote
claude plugin install exza-remote@exza-remote-marketplace
~~~

[Full setup guide](../../docs/CLAUDE_CODE_PLUGIN.md) · [Deutsch](../../docs/CLAUDE_CODE_PLUGIN.de.md)


EXZA Remote uses the same published MCP server as the existing ChatGPT plugin: **https://remote.exza.de/mcp**. The server lists 84 tools; availability still depends on the selected device, OAuth scopes and host permissions.

## Claude.ai / Claude Desktop / Cowork
To use a normal Claude.ai custom connector, enter the remote MCP URL instead of uploading a ZIP. For Anthropic's public directory, use the developer portal and the GitHub-hosted plugin; standalone ZIP uploads are available in certain organization-owned marketplaces.
1. Open Claude **Customize > Connectors > + Add > Add custom connector**.
2. Enter **EXZA Remote – Computer Control**.
3. Enter **https://remote.exza.de/mcp**. Proceed with OAuth authentication, choosing Claude's published OAuth identity or automatic client registration as offered by Claude.
4. Sign into the EXZA account, choose the paired computer and review the requested permissions.
5. Start EXZA Remote Connection on that computer; physically press **Y** to approve the session or **N** to deny.
6. Enable the connector in the conversation and ask Claude to check **exza_status** first.

Free accounts may have limits on the number of custom connectors. Team and Enterprise may require administrator setup.

## Claude Code — actual plugin
The enclosed Claude Code plugin contains a **.claude-plugin/plugin.json**, a **.mcp.json** using the HTTP transport and two setup/safety skills. No credentials, local access tokens or EXZA binaries are bundled.

Extract EXZA-Remote-Claude-Code-Plugin-RC50.zip. Test a single Claude Code session with:
```bash
claude --plugin-dir /path/to/exza-remote
```

To permanently install from the separate local marketplace ZIP, extract it and run:
```bash
claude plugin marketplace add /path/to/exza-remote-marketplace
claude plugin install exza-remote@exza-remote-marketplace
```

Then use **/mcp** to check connection and complete OAuth. If the Claude.ai connector already appears automatically in Claude Code, avoid adding the same MCP twice.

Without this plugin, a Claude Code user can instead run:
```bash
claude mcp add --transport http exza-remote --scope user https://remote.exza.de/mcp
```

## Permission boundaries
Claude and EXZA each enforce authorization. EXZA uses an account, explicitly selected device, OAuth read/write scopes, a physical terminal Y/N decision each local agent session, and the operating system's security rules. Never share PINs, passwords or OAuth tokens in prompts. Powerful tools require deliberate user intent. This is an EXZA Remote third-party integration, not an Anthropic product.

## RC50 client update & Anthropic directory submission

EXZA Remote Connection **1.9.0-rc50** fixes Windows full-window-title focus and verified Unicode/long text input in compatible Windows editors. The remote MCP endpoint and its **84 server tool definitions** are unchanged.

For **Anthropic's public directory** use [the submission portal](https://claude.ai/directory/manage) with this [GitHub-hosted plugin folder](../plugins/exza-remote), or submit a **single remote MCP connector** pointing to https://remote.exza.de/mcp. A suitable paid Claude subscription is required for submission.

**[Download standalone Claude plugin ZIP RC50](https://remote.exza.de/downloads/exza-remote-claude-code-plugin-rc50.zip)** · [Download Windows/Mac/Linux RC50 client](https://remote.exza.de/downloads/exza-remote-client-rc50.zip)

The **marketplace ZIP** is for local/organization marketplace setup, **not** for submitting a single plugin.

