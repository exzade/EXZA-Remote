# EXZA Remote for Claude Code — Remote MCP computer control

**Use Claude Code with your own Mac, Windows PC or Linux computer.** EXZA Remote connects supported AI clients to an owner-authorized device through an OAuth-protected MCP service. The published server lists **84 tool definitions**, subject to your account permissions, operating system and connected device.

[EXZA Remote website](https://remote.exza.de/) · [Create your EXZA account](https://remote.exza.de/app/?register=1&utm_source=github&utm_medium=repository&utm_campaign=claude_code) · [Explore 84 tools](https://remote.exza.de/tools/) · [German guide](CLAUDE_CODE_PLUGIN.de.md)

## Install in two commands

Run these in a terminal with **Claude Code already installed**:

~~~bash
claude plugin marketplace add exzade/EXZA-Remote
claude plugin install exza-remote@exza-remote-marketplace
~~~

Then open Claude Code and type `/mcp` to authorize EXZA Remote using the normal OAuth sign-in. No standalone `npx exza-remote` package exists; the plugin connects to the official hosted HTTPS endpoint.

## Connect your computer

1. Create or sign in to your EXZA Remote account at [remote.exza.de](https://remote.exza.de/app/?register=1&utm_source=github&utm_medium=repository&utm_campaign=claude_code).
2. Install and start the EXZA Remote Connection client on the computer you own or are authorized to administer. See the [official installation guide](GETTING_STARTED.md).
3. Pair the device using the six-digit code shown in your local terminal and the EXZA web dashboard, if prompted.
4. Review the account and device shown in the terminal, then **physically press Y** to authorize that local session, or **N** to deny. Keep the terminal open while working.
5. In Claude Code, open `/mcp` and complete EXZA OAuth with the intended device and appropriate read/write permissions.
6. Start safely: **“Is my EXZA Remote computer connected? Show the operating system and status only.”**

### Example tasks

- **System:** “Check my connected Windows or Mac computer's CPU, memory and running processes.”
- **Files:** “List the files in my approved EXZA workspace without changing anything.”
- **Apps:** “Show installed apps on my connected computer.”
- **Browser:** “Open https://example.com in the browser on my connected PC.”
- **Development:** “After checking the selected project directory, run the exact test command I approve and report the output.”

## What is included

The plugin in [`plugins/exza-remote/`](../plugins/exza-remote) contains a Claude Code manifest, the EXZA Remote `https://remote.exza.de/mcp` server configuration, two safety/onboarding skills, logo and license. **This GitHub repository does not contain the proprietary server application, device credentials, private source code or tokens.**

**Claude.ai / Claude Desktop / Cowork:** These use a custom remote MCP connector rather than installing this Claude Code plugin. Add `https://remote.exza.de/mcp` via Claude's connector settings and sign in with EXZA OAuth.

## Trust and limitations

- All device actions require a valid EXZA account, a paired device and a locally authorized session. Sensitive tools require `computer:write` and applicable Claude/OS approvals.
- A tool shown in the public catalog is **not** proof that any device is online or that a given account can execute it.
- Windows elevated windows and macOS accessibility/privacy restrictions still apply. Remote control is not a bypass of operating-system permissions.
- EXZA Remote is an independent third-party service, **not** an official Anthropic-approved directory listing.
- EXZA's free tier and optional paid plans are shown in the [official customer portal](https://remote.exza.de/); Claude usage or subscriptions are separate. Check current prices before signing up.

## Troubleshooting and support

- Run `claude plugin list` and `claude plugin marketplace list` to check installation.
- Open `/mcp` in Claude Code and confirm OAuth and the selected device.
- If the computer is offline, restart the EXZA Connection client and physically approve the new session; shutting down Windows ends its local session normally.
- Do not put login passwords, pairing PINs or OAuth access tokens in GitHub issues.

[Help center](https://remote.exza.de/help) · [Privacy](https://remote.exza.de/legal/datenschutz.html) · [Terms](https://remote.exza.de/legal/nutzungsbedingungen.html) · [Security reporting](../SECURITY.md) · **info@exza.de**

## RC50 client update & Anthropic directory submission

EXZA Remote Connection **1.9.0-rc50** fixes Windows full-window-title focus and verified Unicode/long text input in compatible Windows editors. The remote MCP endpoint and its **84 server tool definitions** are unchanged.

For **Anthropic's public directory** use [the submission portal](https://claude.ai/directory/manage) with this [GitHub-hosted plugin folder](../plugins/exza-remote), or submit a **single remote MCP connector** pointing to https://remote.exza.de/mcp. A suitable paid Claude subscription is required for submission.

**[Download standalone Claude plugin ZIP RC50](https://remote.exza.de/downloads/exza-remote-claude-code-plugin-rc50.zip)** · [Download Windows/Mac/Linux RC50 client](https://remote.exza.de/downloads/exza-remote-client-rc50.zip)

The **marketplace ZIP** is for local/organization marketplace setup, **not** for submitting a single plugin.

