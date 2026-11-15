---
name: safe-workflow
description: Safely use EXZA Remote MCP tools for approved files, GUI, browser and terminal work while respecting user and OS permissions.
---
# EXZA Remote — safe workflow

Use the least-privileged tool needed for the user's request. The connected EXZA account, selected device, local terminal approval and host approval are independent controls.

- Status: exza_status. Read OS/system status with exza_system_health, exza_desktop_active_window, exza_desktop_windows or other available read tools.
- Managed files: exza_home_list, exza_home_read_text, exza_home_write_text, exza_home_edit_block and hash verification. Avoid unnecessary shell commands, hidden folders and overwrites.
- Browser: exza_browser_open or exza_desktop_browser_choose with a normal HTTPS URL. Opening a page does not authorize uploading data or submitting web forms.
- GUI: use the display and window tools to identify the correct target before typing, clicking, dragging or using shortcut sequences. OS integrity restrictions on admin windows remain in force.
- Terminal: exza_run_command is high risk. Use it only for a concrete approved request and don't try to bypass purpose-built permissions.
- Email and destructive operations: never send, trash, overwrite or trigger a payment without specific user intent and applicable approval.

Separate a tool call reporting success from independent visual verification. Report timeouts and partial work accurately. 84 tools are registered at the live server, but the available set depends on each account, host and local operating system.
