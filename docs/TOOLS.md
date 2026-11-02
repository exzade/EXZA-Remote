# EXZA Remote MCP tool catalog

The current EXZA Remote integration registers **59 tool interfaces**. This catalog describes their *intended capabilities*, not an assurance that every tool is enabled, supported on every operating system, or executable without authorization.

> **Safety and accuracy:** All tools are constrained by device scope, platform support, the active session, permission grants and relevant review controls. Some actions can change data or communicate externally. Follow current on-device approval prompts and the [official help center](https://remote.exza.de/help).

## Connection and general information

| Tool | Purpose |
| --- | --- |
| `exza_status` | Check paired device connection and activity |
| `exza_system_info` | Read supported OS and hardware information |
| `exza_process_list` | Inspect a bounded process summary |
| `exza_list_files` | List files inside the owner-authorized scope |
| `exza_browser_open` | Open a permitted HTTP(S) URL on the computer |

## Managed home-folder operations

| Tool | Purpose |
| --- | --- |
| `exza_home_info` | Inspect metadata for an allowed file or folder |
| `exza_home_copy` | Copy a supported file without overwrite |
| `exza_home_search` | Search allowed file and folder names |
| `exza_home_trash` | Move an explicitly approved item to recoverable trash |
| `exza_home_trash_list` | Inspect the private recoverable-trash index |
| `exza_home_restore` | Restore an item from recoverable trash |
| `exza_home_list` | Browse a managed home subfolder |
| `exza_home_mkdir` | Create a folder in managed scope |
| `exza_home_read_text` | Read bounded text from an allowed file |
| `exza_home_edit_block` | Edit a uniquely matched text span with integrity check |
| `exza_home_write_text` | Create or update a supported text file with checks |
| `exza_home_move` | Move or rename a supported item without overwrite |
| `exza_create_downloads_folder` | Create a directly named Downloads folder |
| `exza_list_external_folder` | List names in an explicitly approved user folder |
| `exza_home_read_multiple_text` | Read several permitted text files in one request |

## File and interactive-terminal interfaces

| Tool | Purpose |
| --- | --- |
| `exza_read_file` | Read a local file in bounded chunks |
| `exza_write_file` | Create or overwrite a file subject to permission and review |
| `exza_run_command` | Execute an approved local shell command |
| `exza_start_job` | Start a managed terminal job |
| `exza_job_status` | Read managed-job progress and output |
| `exza_stop_job` | Stop one managed job |
| `exza_process_start` | Start an interactive, owner-authorized process |
| `exza_process_output` | Read bounded output from that process |
| `exza_process_input` | Send approved input to that process |
| `exza_process_sessions` | List managed interactive sessions |
| `exza_process_stop` | Stop one managed interactive process |

## Desktop, clipboard and mail (platform dependent)

| Tool | Purpose |
| --- | --- |
| `exza_desktop_windows` | List supported visible application windows |
| `exza_desktop_focus` | Focus an approved application window |
| `exza_desktop_type` | Type approved text into the active application |
| `exza_desktop_shortcut` | Send an approved keyboard shortcut |
| `exza_clipboard_read` | Read the clipboard with required consent |
| `exza_clipboard_write` | Write to the clipboard with required permission |
| `exza_desktop_apps` | List installed supported macOS apps |
| `exza_desktop_launch` | Launch a supported app |
| `exza_email_preview` | Preview a proposed message without sending |
| `exza_email_draft` | Open a supported email draft after approval |
| `exza_email_send` | Send an approved message via a supported local integration |

## Commander file/search utilities

| Tool | Purpose |
| --- | --- |
| `exza_commander_info` | Read metadata in authorized commander scope |
| `exza_commander_list` | Page through entries in an authorized folder |
| `exza_commander_mkdir` | Create a directory without overwriting |
| `exza_commander_move` | Move or rename a supported item |
| `exza_commander_copy` | Copy an allowed file without overwrite |
| `exza_commander_append` | Append text with a content-integrity check |
| `exza_commander_pdf` | Generate a basic text-based PDF in allowed scope |
| `exza_commander_edit` | Edit one matching text span with integrity check |
| `exza_commander_search_start` | Start a bounded name/content search |
| `exza_commander_search_next` | Read paginated search results |
| `exza_commander_search_stop` | Discard search results and the session |
| `exza_commander_search_list` | List open search sessions and statuses |
| `exza_commander_get_config` | Inspect permitted search preferences |
| `exza_commander_set_config` | Adjust allowed search count/depth preferences |
| `exza_commander_recent_calls` | View redacted local activity history |
| `exza_commander_usage` | Summarize recent local tool calls |
| `exza_task_update` | Show task status in the local terminal |

## About access and support

- Use the official [customer portal](https://remote.exza.de/app/) to pair and manage your devices.
- Permission-sensitive actions may require an additional local or platform confirmation.
- Several desktop/mail actions are macOS-specific; [platform differences](PLATFORMS.md) apply.
- Some operations have file-size, scope, rate, or session limits.
- Neither this catalog nor a tool name is permission to access someone else’s computer.

For product documentation, visit [EXZA Remote](https://remote.exza.de/).
