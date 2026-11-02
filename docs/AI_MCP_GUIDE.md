# Connect ChatGPT or Claude to your computer using MCP

**A practical introduction to AI-assisted local workflows with EXZA Remote.**

[EXZA Remote website](https://remote.exza.de/) · [Open customer portal](https://remote.exza.de/app/) · [Official help center](https://remote.exza.de/help) · [Security information](../SECURITY.md)

## Why connect an AI assistant to your own computer?

An AI assistant can help explain code, review diagnostics, and plan workflows. But in an ordinary chat, you often need to manually copy file contents and terminal results back and forth. With a supported **Model Context Protocol (MCP)** connection, the assistant can request specific, authorized tools on a computer you own or administer.

**EXZA Remote** provides a remote MCP endpoint, an account dashboard, and a local computer client. The connection is tied to a paired computer. Protected operations depend on access scope, user permission, device support, and approvals.

It is **not** an invitation to give AI unrestricted access to your computer.

## Get connected

1. Visit [remote.exza.de](https://remote.exza.de/) and sign in or create an account.
2. In [My Devices](https://remote.exza.de/app/), choose the installation flow for your operating system.
3. Run the official EXZA Remote computer client. Keep its terminal window available while connected.
4. Enter the six-digit pairing code in the portal. Review the request and confirm it locally with the documented **Y** action; reject with **N**.
5. In an AI client that permits custom MCP connections, configure:
   - **Name:** EXZA Remote
   - **Server URL:** `https://remote.exza.de/mcp`
   - **Authentication:** EXZA account (OAuth)
6. Review the requested permissions and paired device before approving access.
7. Start with a read-only status request.

**Compatibility:** Custom MCP connection features depend on the provider's current account plan, product interface, and workspace policies. Windows, Linux, and macOS clients can have different capabilities; consult the [platform matrix](PLATFORMS.md).

## Three safe workflows to try

### 1. Verify your connection

> Is my EXZA Remote computer online? Show the device status. Do not modify anything.

### 2. Understand an allowed project folder

> List the top-level files in my explicitly authorized test project folder. Summarize the structure, but do not read credentials or write any files.

### 3. Run a development check with approval

> Suggest one harmless project test command and explain exactly what it will do. Do not execute it until I approve it.

For more scenarios, see the [workflow examples](USE_CASES.md).

## What can EXZA Remote access?

Its integration currently registers **59 MCP tool interfaces** across connection status, files, terminal jobs, processes, supported desktop interaction, and other owner-authorized operations. Registration does not imply all 59 work on every operating system or without confirmation.

The computer owner retains important responsibilities: limit the authorized scope, review commands and file changes, and disconnect when access is no longer needed.

## How do I disconnect?

Use the device controls in your customer portal to manage or revoke the connection. Stopping the local computer client ends its active connection. For account-specific or installation help, use the [Help Center](https://remote.exza.de/help).

## Common questions

**Is EXZA Remote open source?** No. The public GitHub repository documents a proprietary product; the private server and client source code is not published.

**Does it require admin/root access?** Follow the official OS-specific installer. Do not grant extra operating-system rights or bypass local security controls.

**Does it support any AI assistant?** Only compatible clients that support the required remote MCP and authorization flow. Support and plan eligibility can change.

**Does it cost money to try?** The product advertises a free tier of 10,000 successful tool calls per EXZA account per UTC month; see the website for current offer terms and premium pricing.

**Can ChatGPT perform dangerous operations automatically?** Sensitive operations are subject to platform and local permission/approval checks. Always inspect requests before approving them.

---

**EXZA Remote — Your computer. Your control.** [Get started](https://remote.exza.de/app/).
