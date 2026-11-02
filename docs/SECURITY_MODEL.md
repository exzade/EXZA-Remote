# Security and user control

EXZA Remote is designed to require **account, device, and action-level authorization** rather than silently granting a chatbot permanent access to a computer.

## Layered control

1. **Account authentication:** A user signs in to an EXZA account.
2. **Device pairing:** The owner starts the computer client, enters its one-time code in the portal, and confirms locally.
3. **AI-client authorization:** A compatible AI client completes the EXZA OAuth flow with an authorized device and appropriate scopes.
4. **Action checks:** Available tools are constrained by device support, owner-authorized scope, and requested permissions.
5. **Sensitive-action approvals:** Certain operations may need additional, explicit approval, including native prompts or local controls.
6. **Revocation/disconnection:** The user can manage access in the dashboard and end the local client connection.

## Good practice

- Pair only computers you own or are allowed to operate.
- Verify the account, device, scope, requested command, and destination before approval.
- Treat shell commands, clipboard content, file edits, and outgoing messages as potentially sensitive.
- Do not use shared or public AI conversations to pass passwords, tokens, PINs, or other credentials.
- Keep the local OS, runtime, browser, and client updated through trusted sources.
- Close or disconnect the client when remote access is no longer required.
- If behavior looks unexpected, revoke the device/client session and contact support.

## Scope of this repository

This public repository contains **product documentation and non-secret marketing resources only**. It does not include:

- Server or agent source code, private plugins, infrastructure or deployment files.
- Customer databases, payment data, or private business records.
- Access tokens, OAuth credentials, session cookies, device keys, internal logs, or recovery material.
- Security procedures that would bypass existing controls.

## Vulnerabilities

See the repository [Security Policy](../SECURITY.md). Report security issues privately to **info@exza.de**, not in a public issue. This documentation is not a security certification or guarantee that no vulnerabilities exist.

Official policy pages: [Privacy](https://remote.exza.de/legal/datenschutz.html) · [Terms](https://remote.exza.de/legal/nutzungsbedingungen.html).
