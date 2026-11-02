# Platform compatibility

EXZA Remote provides installation and setup paths for **macOS, Windows, and Linux**. The same public MCP service is used, but native behavior and available tools differ.

| Feature area | macOS | Windows | Linux |
| --- | --- | --- | --- |
| EXZA account, web portal, and OAuth/MCP service | Supported | Supported | Supported |
| Client installation path | Available; tested on a connected Mac | Available; platform-specific validation recommended | Available; platform-specific validation recommended |
| Device pairing and connection | Tested on macOS | Provided; verify with your target setup | Provided; verify with your target setup |
| File and terminal features | Permission-dependent | Permission- and implementation-dependent | Permission- and implementation-dependent |
| Desktop/window/keyboard integrations | Supported for selected tools | Do not assume macOS desktop-tool parity | Do not assume macOS desktop-tool parity |
| Local mail integrations | Selected macOS capabilities | Availability varies | Availability varies |

**Compatibility note:** Current native end-to-end verification is strongest on macOS. Windows/Linux client paths are available, but we do not claim the full 59-tool set has been independently end-to-end tested on each OS.

## Requirements

Review the official [installation help](https://remote.exza.de/help) for current runtime prerequisites, supported commands, permissions, and known limitations. The client runs on the computer you want to control, not on the phone you use to view the web portal.

## AI clients

- **ChatGPT:** requires a compatible configuration supporting the relevant remote MCP connector and user authorization.
- **Claude:** requires supported custom connector configuration and appropriate granted permissions.
- **Other MCP clients:** compatibility depends on their implementation and authentication support.

Neither EXZA Remote nor this repository is an official product of OpenAI or Anthropic. The AI services retain control over their own availability, requirements, and permission prompts.

For setup problems, use the [official help center](https://remote.exza.de/help) and report your exact OS and client version without uploading private system details.
