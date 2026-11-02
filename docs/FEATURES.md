# Features and MCP tool categories

EXZA Remote connects a user-owned computer to a compatible AI client through a protected, paired connection. The current integration **registers 59 MCP tool interfaces**, spanning several categories. Tool registration does not imply unrestricted execution or cross-platform feature parity.

## Connection and system status

- Inspect the paired computer's connection state.
- Obtain supported operating-system and system metadata.
- Inspect a bounded selection of active processes.
- Understand which local capabilities and permissions are available.

## Files and workspace

- List and inspect files in the device-authorized area.
- Read supported text files and bounded file ranges.
- Search files or file names within allowed scope.
- Where authorized, create, move, copy, edit, or recover supported files.
- Generate certain outputs (such as simple documents) using approved local workflows.

**Boundary:** Files remain subject to the local owner's permitted scope and relevant action approvals. EXZA Remote is not a blanket grant of access to every file on the computer.

## Terminal and long-running operations

- Run owner-approved terminal commands where permitted.
- Start, monitor, and stop supported managed jobs.
- Inspect bounded job or process output.
- Execute development, diagnostic, and automation workflows with appropriate review.

**Boundary:** Commands can change files, install programs, or access sensitive information. Every suggested command should be independently reviewed before approval.

## Desktop, clipboard, and applications

- Inspect supported application/window information.
- Focus or launch supported apps where the device and operating system permit it.
- Use supported desktop typing and keyboard actions when expressly authorized.
- Perform supported clipboard operations with the appropriate permissions.

Some desktop integrations are **macOS-only**; see [Platform support](PLATFORMS.md).

## Communication workflows

- Prepare or preview supported email content.
- Where the platform and permissions allow, draft or send messages through approved local tools.

Sending email is an external, potentially irreversible action. **Recipient and message review are essential.** Do not assume email tools exist on every operating system.

## Security and control

- Device-specific pairing with a time-limited code.
- Local confirmation when pairing a computer.
- OAuth authorization for compatible AI clients.
- Additional permission or approval gates for sensitive actions.
- Device and session controls in the EXZA customer dashboard.

## Usage and account management

- Account login, device list, and connection management.
- Usage and plan information.
- Documentation, platform help, and support options.

## Important limitations

1. **59 registered interfaces ≠ 59 universal OS features.** The supported set varies by OS, device state, granted scopes, and client capabilities.
2. A connection alone does not imply approval for all actions.
3. Clients must be actively paired and reachable; local terminal/client uptime matters.
4. Third-party AI platform compatibility, limits, or custom MCP availability can change.
5. EXZA Remote is not an unattended access bypass, privilege escalation tool, or substitute for system security controls.

For authoritative, current capabilities, read the [official help center](https://remote.exza.de/help) and test the exact workflow with a low-risk request.
