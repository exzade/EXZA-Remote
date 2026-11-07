![EXZA Remote logo](https://remote.exza.de/assets/logo-128.webp)

# EXZA Remote — AI Computer Commander

**Your computer. Your control.** Secure, owner-authorized remote computer tools for supported ChatGPT, Claude and other MCP clients, discoverable through Glama.

EXZA Remote connects an AI client to a computer **you own or are explicitly authorized to operate**. Install the official EXZA Remote Connection client on macOS, Windows or Linux, pair the computer to your account, and control access through OAuth scopes and local owner approvals. No open SSH port, port forwarding or public access to private computer files is required.

**[Get started](https://remote.exza.de/app/?register=1)** · **[Official website](https://remote.exza.de/)** · **[Glama connector](https://glama.ai/mcp/connectors/de.exza.remote/exza-remote)** · **[Help center](https://remote.exza.de/help#manual-glama)**

| Key fact | EXZA Remote |
|---|---|
| MCP endpoint | **https://remote.exza.de/mcp** |
| Transport | Streamable HTTP over HTTPS |
| Authentication | EXZA OAuth; account and paired device required |
| Supported computers | macOS, Windows, Linux (capabilities vary) |
| Exposed interfaces | **59 MCP tools** |
| Device security | Six-digit pairing, scoped OAuth, owner confirmation where required |
| Distribution | Hosted, proprietary EXZA service — not an npm MCP package |

## How it works

~~~text
Your AI client (ChatGPT / Claude / compatible MCP client)
          │
          ▼
EXZA Remote MCP endpoint — HTTPS + OAuth
          │
          ▼
EXZA account, scope and paired-device authorization
          │
          ▼
Outbound secure connection to your own computer
          │
          ▼
Local owner approval when required
          │
          ▼
Approved files • system status • terminal • desktop tools
~~~

EXZA Remote's computer client runs as a **foreground terminal connection**. Keeping it open keeps that session available; disconnecting or closing it ends the active connection. The local computer remains under its owner's control.

## Installation and first connection

### Step 1 — Create your EXZA account

Register at **[remote.exza.de](https://remote.exza.de/app/?register=1)**, complete any required email verification and open **My Devices** in the [customer portal](https://remote.exza.de/app/).

### Step 2 — Install the official computer client

**Prerequisites:** Node.js **22+**, npm, internet access and an authorized computer. If necessary, obtain Node.js from [nodejs.org](https://nodejs.org/en/download).

**macOS and Linux — Terminal:**

~~~sh
node --version
npm --version
curl -fsSL https://remote.exza.de/install.sh -o exza-install.sh
sh exza-install.sh
~~~

**Windows 10/11 — PowerShell:**

~~~powershell
node --version
npm --version
curl.exe -fsSL https://remote.exza.de/install.ps1 -o exza-install.ps1
powershell -NoProfile -ExecutionPolicy Bypass -File .\exza-install.ps1
~~~

EXZA's official installers download the client over HTTPS and **verify its SHA-256 checksum**. You can inspect the [Unix installer](https://remote.exza.de/install.sh) or [Windows installer](https://remote.exza.de/install.ps1) before running it. No GitHub clone, root/admin installation or unofficial npm package is needed.

### Step 3 — Pair the computer and approve access

The terminal provides a **temporary six-digit pairing code**. Enter it in your EXZA dashboard under **My Devices** and confirm the displayed device/account information. Accept the local pairing request with **Y**, or decline with **N**.

The illustration below shows the general connection flow (the exact terminal appearance may vary by platform and client version):

~~~text
╔══════════════════════════════════════════════╗
║ EXZA REMOTE CONNECTION  |  SECURE LINK        ║
╚══════════════════════════════════════════════╝

Computer: <your computer name>
Remote actions require permission from this computer.

My Devices: Enter the temporary 6-digit code
Owner approval: Y = allow   |   N = deny

Keep this terminal open while connected.
Close or disconnect to end the active computer session.
~~~

**A pairing PIN is not an API key, and it must never be used as an OAuth access token.**

### Step 4 — Connect your MCP client via OAuth

In a supported ChatGPT, Claude, Glama Inspector or other remote-MCP client, create an **EXZA Remote** connection using:

~~~text
Server name: EXZA Remote
MCP URL:     https://remote.exza.de/mcp
Transport:   Streamable HTTP
Sign-in:     EXZA OAuth
~~~

Complete the EXZA OAuth login, select your paired computer and review the permissions granted. Start with **computer:read** when possible, and use **computer:write** only for explicitly authorized actions. Client availability and menu labels vary by plan, product and workspace.

**In Glama:** open the [EXZA Remote connector](https://glama.ai/mcp/connectors/de.exza.remote/exza-remote) and use **Connect / Inspector** where available. Authorize **your own** EXZA account for personal tool testing. A directory listing alone does not connect to or share a computer.

**Optional Claude Code command** (if its remote-MCP flow is supported by your Claude setup):

~~~sh
claude mcp add --transport http exza-remote https://remote.exza.de/mcp
claude mcp list
~~~

Use the direct HTTPS endpoint and follow OAuth in the client. Do **not** use a directory-generated “npx exza-remote” installation command: EXZA Remote is not distributed as such a package.

### Step 5 — Start with a connection-status check

- **exza_get_connection_status** — a safe connection-status test using the **computer:read** OAuth scope.
- **exza_get_system_info** — request system details only when needed; the current EXZA server requires **computer:write** authorization for these potentially private details.
- **exza_list_home_files** — list permitted managed-home folder names only when needed; this privacy-sensitive read also requires **computer:write** authorization.

**Important:** A tool can be read-only in its effect on files but still require elevated OAuth authorization to access sensitive information. Do not grant write scopes just to improve a directory health check.

Glama's presentation may use these consistent names; existing ChatGPT/Claude integrations may use earlier names (such as **exza_status**) for the same protected operations.

## Available MCP tools — 59 interfaces

The published catalog includes 59 tools in the following functional groups. **Availability depends on the operating system, client, device permissions and subscription limits.** A listed tool is not automatically authorized, and some tools may change or delete data.

### Connection and system status (3)

| Tool | Capability |
|---|---|
| **exza_get_connection_status** | Read the current EXZA connection and approval status. |
| **exza_get_system_info** | Inspect operating-system, CPU, memory, uptime and network details. |
| **exza_update_task_progress** | Update a task's visible progress status in the local EXZA terminal. |

### Workspace files (3)

| Tool | Capability |
|---|---|
| **exza_list_workspace_files** | List files inside the restricted EXZA workspace. |
| **exza_read_workspace_file** | Read an authorized workspace file using bounded chunks. |
| **exza_write_authorized_file** | Create or overwrite an approved file; may replace existing data. |

### Managed home folders and files (14)

| Tool | Capability |
|---|---|
| **exza_get_home_file_info** | Read metadata for one managed-home file or folder. |
| **exza_copy_home_file** | Copy one managed-home item without removing the original. |
| **exza_search_home_files** | Search permitted managed folders by filename. |
| **exza_trash_home_file** | Move an authorized managed-home item into the EXZA recycle bin. |
| **exza_list_home_trash** | List recyclable items without restoring them. |
| **exza_restore_home_file** | Restore an approved file from the EXZA recycle bin. |
| **exza_list_home_files** | List visible entries in a permitted managed-home folder. |
| **exza_create_home_directory** | Create a new directory inside a managed-home area. |
| **exza_read_home_text** | Read a bounded, permitted text file. |
| **exza_edit_home_text** | Replace a unique text span using an expected file checksum. |
| **exza_write_home_text** | Create or replace an approved managed-home text file. |
| **exza_move_home_file** | Move or rename a managed-home item without overwriting. |
| **exza_create_downloads_folder** | Create a new direct subfolder in Downloads. |
| **exza_read_home_text_files** | Read several approved text files in a bounded batch. |

### Approved Commander file operations and searches (16)

| Tool | Capability |
|---|---|
| **exza_get_commander_file_info** | Inspect metadata for one explicitly authorized path. |
| **exza_list_commander_files** | Page through file and folder names in an approved directory. |
| **exza_create_commander_directory** | Create an approved directory without overwriting. |
| **exza_move_commander_file** | Move or rename an approved file or directory. |
| **exza_copy_commander_file** | Copy an authorized file, preserving the original. |
| **exza_append_commander_file** | Append text guarded by a file checksum. |
| **exza_create_commander_pdf** | Create a simple PDF in an approved location. |
| **exza_edit_commander_file** | Edit an exact text span using checksum protection. |
| **exza_start_commander_search** | Start a bounded, asynchronous filename/content search. |
| **exza_get_commander_search_results** | Fetch another page of results from an existing search. |
| **exza_stop_commander_search** | Stop an existing search and clear temporary search state. |
| **exza_list_commander_searches** | List current search sessions and their state. |
| **exza_get_commander_preferences** | Read supported Commander search preferences. |
| **exza_set_commander_preferences** | Change supported search preferences. |
| **exza_list_commander_call_history** | Inspect redacted, recent Commander tool-call records. |
| **exza_get_commander_usage** | Read Commander tool-use counts and summaries. |

### Terminal commands, jobs and processes (10)

| Tool | Capability |
|---|---|
| **exza_run_shell_command** | Execute one approved shell command; potentially consequential. |
| **exza_start_background_job** | Start a monitored background shell job and return its ID. |
| **exza_get_background_job_status** | Read progress and bounded output for an existing job. |
| **exza_stop_background_job** | Stop an existing background job. |
| **exza_list_system_processes** | Read a bounded system-process snapshot. |
| **exza_start_interactive_process** | Start a supervised interactive shell process. |
| **exza_read_interactive_process_output** | Read output from an interactive process session. |
| **exza_send_interactive_process_input** | Send input to an active interactive process. |
| **exza_list_interactive_processes** | List EXZA-owned interactive process sessions. |
| **exza_stop_interactive_process** | Stop a selected interactive process session. |

### Desktop applications and browser (7)

| Tool | Capability |
|---|---|
| **exza_list_desktop_windows** | List visible desktop windows where supported. |
| **exza_focus_desktop_window** | Bring an approved desktop window into focus. |
| **exza_type_desktop_text** | Type approved text into the focused application. |
| **exza_send_desktop_shortcut** | Send a keyboard shortcut to the focused application. |
| **exza_list_desktop_apps** | List supported installed desktop applications. |
| **exza_launch_desktop_app** | Launch an approved desktop application. |
| **exza_open_browser_url** | Open an HTTP(S) URL in the authorized computer's browser. |

### Clipboard (2)

| Tool | Capability |
|---|---|
| **exza_read_clipboard_text** | Read permitted clipboard text; it may contain sensitive data. |
| **exza_write_clipboard_text** | Replace clipboard text, overwriting its previous value. |

### Email workflows (3)

| Tool | Capability |
|---|---|
| **exza_preview_email_message** | Prepare a non-sending preview of an email. |
| **exza_create_email_draft** | Open an editable email draft for review. |
| **exza_send_email_message** | Send an explicitly approved email; transmission cannot be recalled. |

### External authorized folders (1)

| Tool | Capability |
|---|---|
| **exza_list_external_home_folder** | List names in a separately approved home directory outside the default workspace. |


## Example workflows

**Read-only first.** These prompts illustrate safe intentions and do not bypass tool permissions.

- “Check whether my connected laptop is online.”
- “List filenames in my approved Documents folder.”
- “Show CPU and memory information for my connected computer.”
- “Find a text document and summarize its contents without modifying it.”
- “Prepare an email draft for my approval; do not send it.”
- “After I approve, execute the requested maintenance command and report the job status.”

## Security and privacy by design

**Owner-controlled access.** EXZA requires a separate user account and an associated computer. OAuth permission scopes, account/device boundaries, and local computer approval protect potentially sensitive operations. **Destructive** safety badges indicate that a tool may change state; they are not error indicators.

**Glama's publisher health check is discovery-only.** Its designated profile can authenticate and list tool metadata but **cannot execute computer tools**. Other users connect separately with their own EXZA credentials and device permission.

**Direct Inspector vs optional Glama Gateway.** Glama's browser Inspector can test a direct connection. An optional Gateway adds its own credentials and JSON-RPC logging, potentially including tool arguments, results and timestamps. Review Glama's privacy and terms before transmitting confidential files or terminal output through a third-party gateway.

**Independent platforms.** EXZA Remote is not owned by, affiliated with or endorsed by OpenAI, Anthropic, Glama or mcptry. Their terms, subscriptions and data processing are separate.

## Common troubleshooting

| Symptom | What to check |
|---|---|
| Computer not listed | Keep the official client running, verify pairing under My Devices, and check device status. |
| HTTP 401 / sign-in required | Complete EXZA OAuth in the client. Do not paste the device PIN as a token. |
| Tool shown but access denied | Check EXZA account, selected device, OAuth scopes and any owner-approval prompt. |
| Write action blocked | Only grant computer:write if necessary and approved by the device owner. |
| Destructive warning | This is an intentional safety flag for potentially changing actions. |
| Glama test profile cannot execute | By design. Use a separate, personally authenticated Inspector session for real tool testing. |
| Terminal disconnected | Start the local client again and complete the required pairing/approval. |
| Gateway privacy concern | Prefer a direct EXZA OAuth connection instead of an optional third-party proxy. |

## Official resources

**[Create an EXZA account](https://remote.exza.de/app/?register=1)** · **[Official Glama listing](https://glama.ai/mcp/connectors/de.exza.remote/exza-remote)** · **[Website](https://remote.exza.de/)** · **[Help and connection walkthrough](https://remote.exza.de/help#manual-glama)** · **[GitHub documentation](https://github.com/exzade/EXZA-Remote)** · **[Contact support](mailto:info@exza.de)**

[Privacy policy](https://remote.exza.de/legal/datenschutz.html) · [Terms of use](https://remote.exza.de/legal/nutzungsbedingungen.html) · [General terms](https://remote.exza.de/legal/agb.html) · [Glama privacy](https://glama.ai/policies/privacy-policy)

**EXZA Remote — Your computer. Your control.**
