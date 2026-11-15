---
name: connect
description: Connect EXZA Remote to an authorized Mac, Windows or Linux computer, verify device binding and report live status safely.
---
# EXZA Remote — connect a verified computer

Use EXZA Remote only when a user expressly wants their own or an authorized computer accessed.

1. Verify the MCP server URL is https://remote.exza.de/mcp. Never request or copy the user's EXZA password, pairing PIN, OAuth code, token or device secret into Claude.
2. Ask the user to open https://remote.exza.de and sign in, start the local EXZA Remote Connection client and select the intended device in the EXZA OAuth flow.
3. The owner must physically press Y for that EXZA terminal session (or N to deny); a fresh Y/N choice is needed after the local terminal restarts. Stopping the terminal ends the connection.
4. On a status request call exza_status first. Don't treat a registered tool as proof that a specific device is online.
5. computer:read and computer:write are separate OAuth permissions. Claude host controls its own tool approval and macOS, Windows and Linux retain OS safety boundaries. Never bypass any of them.
6. When a device is offline, tell the user it is offline; do not claim a server outage. If several devices are paired, use the one explicitly selected through OAuth.
7. For routine work prefer a specific narrow EXZA tool to exza_run_command. Do not run irreversible commands without a concrete user instruction and appropriate approval.

Claude.ai and Claude Desktop use a custom Remote MCP connector. This packaged skill is part of a Claude Code plugin; the ZIP is not a Claude.ai connector import format.
