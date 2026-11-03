# Frequently asked questions

### What is EXZA Remote?

A service that connects a computer you control to compatible AI assistants over MCP, with account, device-pairing, and authorization controls.

### Does EXZA Remote replace ChatGPT or Claude?

No. It is a separate product that provides a controlled computer connection to AI clients that support the required MCP functionality.

### Can I use EXZA Remote directly in ChatGPT Web, without installing Codex?

Yes, **where your ChatGPT web account or workspace supports custom MCP plugins and the necessary actions**. Pair your computer through [EXZA Remote](https://remote.exza.de/app/), then in ChatGPT Web open **Plugins → Add custom MCP server**, enter **`https://remote.exza.de/mcp`**, authorize EXZA OAuth, and select the connection in a supported conversation. No separate Codex installation is required for this route. Read-only or write/computer action availability is controlled by OpenAI's plan and workspace policies; listing in the public plugin directory is separate. See the [ChatGPT Web walkthrough](AI_MCP_GUIDE.md).

### Which AI clients can I use?

ChatGPT, Claude, and potentially other compatible MCP clients. Availability depends on the third-party client's configuration, plan, workspace policies, and authorization support.

### Can I install EXZA Remote on Windows and Linux?

Client setup paths are provided for macOS, Windows, and Linux. Some capabilities are OS-specific; macOS has the strongest currently verified native testing. See [Platforms](PLATFORMS.md).

### Does the client need to remain running?

Yes. Keep the local EXZA client connection open for active computer access. Closing the client ends its active computer connection.

### What does the one-time code do?

It links the computer to your EXZA account when confirmed locally. It is distinct from granting an AI assistant permission to use the device.

### Is my computer completely controlled automatically?

No. The available operations are limited by the operating system, granted capabilities, authorized scope, and applicable approval controls. Always review risky requests.

### How many tools are there?

The current EXZA Remote integration registers **59 MCP interfaces**, with platform and permission-dependent availability.

### Is there a free plan?

Yes. The advertised free allowance is 10,000 successful tool calls per EXZA account per UTC month, shared across AI clients. Refer to the official dashboard for current plan details and fair-use terms.

### Is Premium available?

See the [official product website](https://remote.exza.de/) and dashboard for live pricing, currency, current capabilities, and billing information. This repository does not process payments.

### Is this an open-source project?

No. This public GitHub repository is a documentation and product showcase, not a release of the private EXZA Remote code. See [NOTICE](../NOTICE.md).

### How do I report a problem?

Use the [official Help Center](https://remote.exza.de/help) or contact [info@exza.de](mailto:info@exza.de). Public issues must not contain account data, secret material, or private logs.

### Where can I find ready-made prompt ideas?

See the [EXZA Prompt Library](https://remote.exza.de/prompts/).
