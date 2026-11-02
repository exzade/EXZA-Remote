# Getting started with EXZA Remote

EXZA Remote is an account-based service. The fastest and safest setup path is through the official [website](https://remote.exza.de/) and [customer portal](https://remote.exza.de/app/).

## 1. Set up your EXZA account

- Register or sign in through the official website.
- Complete any required email verification.
- Open **My Devices** in the customer dashboard.
- Do not share your credentials, recovery codes, or browser session data.

## 2. Install the computer client

- Select **macOS**, **Windows**, or **Linux** in the official pairing instructions.
- Use the installer or client package linked by **remote.exza.de**; do not run commands copied from an unverified third-party site.
- Run the client on a computer you own or are authorized to operate.
- Keep the local client/terminal open while you want the computer to remain connected.

See the current [macOS, Windows, and Linux help](https://remote.exza.de/help) for prerequisites and supported installation steps.

## Copy-and-paste installation commands

This GitHub repository is for EXZA Remote's **public product documentation**, not private client/source distribution. Run the official installer on your own or an authorized computer, not on a phone.

**Prerequisites:** [Node.js 22+](https://nodejs.org/) with npm, internet access, and an EXZA account. macOS/Linux also need curl, unzip and a SHA-256 verification utility.

### macOS / Linux — Terminal

\`\`\`sh
node --version
npm --version
curl -fsSL https://remote.exza.de/install.sh -o exza-install.sh && sh exza-install.sh
\`\`\`

### Windows 10/11 — PowerShell (standard user)

\`\`\`powershell
node --version
npm --version
curl.exe -fsSL https://remote.exza.de/install.ps1 -o exza-install.ps1
powershell -NoProfile -ExecutionPolicy Bypass -File .\exza-install.ps1
\`\`\`

The PowerShell execution-policy option applies to this process only. Review the script before running and follow organizational security policies. Windows/Linux tool and end-to-end testing differ from macOS; see [Platforms](PLATFORMS.md).

The installers download the official package from EXZA's HTTPS domain and verify its SHA-256 checksum before running the client. **Keep its terminal open** while connected. Inspect the published [Unix](https://remote.exza.de/install.sh) or [Windows](https://remote.exza.de/install.ps1) script first. No GitHub clone or administrator/root installation is required.

## 3. Pair your computer

1. Start the local EXZA Remote client.
2. Locate the **six-digit security code** shown in its terminal.
3. Enter the code under **My Devices** in your EXZA dashboard.
4. Check the displayed account/request details and confirm the pairing **on your own computer** with the documented local `Y` action; use `N` to reject.
5. Verify that the device appears in your dashboard as connected.

Pairing a computer is separate from granting an AI client permissions. Review both steps.

## 4. Connect an AI client

Where your ChatGPT, Claude, or other compatible MCP account supports custom remote MCP servers:

- Server name: **EXZA Remote**
- HTTPS MCP endpoint: **`https://remote.exza.de/mcp`**
- Authentication: **EXZA account via OAuth**

Follow the platform's current custom-connector instructions. Review all scopes and the selected device during the EXZA authorization process. Availability of custom MCP connections may depend on the AI provider, plan, and workspace settings.

## 5. Test with a safe request

Start with a harmless read-only check, for example:

> Check whether my EXZA Remote computer is connected. Do not make any changes.

Do **not** begin by running a large shell script, modifying personal files, or granting unrestricted desktop access.

## 6. Disconnect

Use the device controls in your EXZA customer portal to disconnect or revoke a device as needed. Stopping/closing the local computer client ends its active connection. If you suspect a compromise, also review your EXZA and AI-client sessions and credentials.

## Troubleshooting

See the [FAQ](FAQ.md) and official [Help Center](https://remote.exza.de/help). When reporting a problem, include OS, approximate time, a sanitized error message, and expected vs. actual behavior. Never publish tokens or private logs.
