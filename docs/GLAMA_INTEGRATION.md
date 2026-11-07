# EXZA Remote × Glama — MCP Directory & Inspector

**New integration · Secure remote MCP · macOS / Windows / Linux**

<a href="https://glama.ai/mcp/connectors/de.exza.remote/exza-remote"><img src="https://remote.exza.de/assets/third-party/glama-mark.webp" alt="Glama MCP directory" width="64" height="64" /></a>

**[Open EXZA Remote on Glama](https://glama.ai/mcp/connectors/de.exza.remote/exza-remote)** · [Create an EXZA account](https://remote.exza.de/app/?register=1) · [Official setup and troubleshooting](https://remote.exza.de/help#manual-glama)

EXZA Remote lets a compatible AI client access **your own approved computer** through an OAuth-protected Model Context Protocol (MCP) server. Glama independently lists the verified connector and provides a browser-based MCP Inspector for discovery and connection testing. EXZA Remote is a proprietary hosted service, **not** an open-source package or a locally installed Glama-hosted server.

## Start in under six steps

1. **Create your EXZA account** at [remote.exza.de](https://remote.exza.de/app/?register=1) and verify your email.
2. **Connect your computer:** install the official EXZA Remote client from the [customer portal](https://remote.exza.de/app/), pair the Mac/Windows/Linux device using the one-time six-digit PIN, and approve the request on the computer with **Y**. Leave the terminal connected.
3. **Open the [verified EXZA Remote Glama connector](https://glama.ai/mcp/connectors/de.exza.remote/exza-remote).** Use Glama's Connect / Inspector flow, where offered, and choose **OAuth**. The canonical direct MCP endpoint is `https://remote.exza.de/mcp` (Streamable HTTP). Do **not** paste your pairing PIN as an API key or bearer token.
4. **Authorize your own EXZA account and paired device.** Start with `computer:read` when possible; only grant `computer:write` for actions you genuinely intend to permit. Follow the device-owner prompts.
5. **Discover tools, then test safely.** In Glama, first inspect the tool list. For an authorized *personal* connection, request the read-only `exza_get_connection_status` tool (legacy name `exza_status`). Glama-specific names may differ from ChatGPT / Claude names while retaining the same permissions.
6. **Use your preferred AI client:** where supported, add EXZA Remote directly using `https://remote.exza.de/mcp` and EXZA OAuth. Alternatively, users who intentionally choose the **Glama Gateway** can use its separately configured connection-profile URL under Glama's own service terms. A public directory listing alone does **not** grant access to a computer.

### What can EXZA Remote do?

**59 registered MCP tool interfaces** cover approved file inspection and management, system and process information, terminal jobs, desktop interactions, and other supported workflows. Actual availability varies by OS, client, EXZA permissions, and device approval; **not all tools are read-only**.

### Privacy and security — please read

- **Account separation:** The Glama publisher's health-check profile may authenticate and list tool definitions but **cannot execute computer tools**. It is not a shared account for visitors. Your own device is accessible only via a separately authorized EXZA connection with the required approvals.
- **Inspector vs Gateway:** A direct browser-based Inspector check is distinct from choosing the **Glama Gateway**. Glama describes Gateway processing that can log **complete JSON-RPC input and output payloads**, including tool arguments, results, timestamps, and managed OAuth credentials. Do not route passwords or confidential file content through a third-party gateway without understanding its data processing.
- **Security:** Files, shell commands, email sending, or other consequential changes require the appropriate EXZA permissions and any required owner confirmation. Destructive badges are **safety warnings**, not proof of a broken connector. A green “Healthy” listing confirms metadata connectivity, not every tool on every device.
- **Independent services:** EXZA Remote is **not affiliated with or endorsed by** Glama, OpenAI, Anthropic or mcptry. Their own subscriptions, terms, and privacy practices remain separate.

[EXZA privacy policy](https://remote.exza.de/legal/datenschutz) · [EXZA terms of use](https://remote.exza.de/legal/nutzungsbedingungen) · [EXZA general terms](https://remote.exza.de/legal/agb) · [Glama privacy policy](https://glama.ai/policies/privacy-policy) · [Glama terms](https://glama.ai/policies/terms-of-service)

**Troubleshooting:** If OAuth, tool discovery, device connection, or permission scopes do not work, see the [official EXZA Glama help](https://remote.exza.de/help#manual-glama). You can contact [EXZA Support](mailto:info@exza.de). Never send pairing PINs, login passwords or refresh tokens to support.

---

# EXZA Remote mit Glama verbinden — Deutsch

**Neu: Glama MCP-Verzeichnis und Inspector für EXZA Remote.**

[**Offiziellen funktionsfähigen Glama-Eintrag öffnen**](https://glama.ai/mcp/connectors/de.exza.remote/exza-remote) · [EXZA-Kundenkonto](https://remote.exza.de/app/?register=1) · [Vollständige deutsche Hilfe](https://remote.exza.de/hilfe#manual-glama)

Mit EXZA Remote können unterstützte KI-Clients nach deiner **ausdrücklichen Freigabe** auf Werkzeuge deines eigenen Computers zugreifen. Glama zeigt den Connector öffentlich an und bietet einen Inspector zur Prüfung der Verbindung.

1. **Bei EXZA anmelden** und die E-Mail bestätigen.
2. **Computer koppeln:** Offiziellen EXZA-Client über das Kundenportal installieren, sechsstellige PIN eingeben, am Computer mit **Y** bestätigen und das Terminal geöffnet lassen.
3. **Glama-Connector öffnen:** Den oben verlinkten, als funktionierend geprüften EXZA-Remote-Eintrag verwenden. Bei Connect/Inspector die **OAuth-Anmeldung** wählen. Die direkte MCP-Adresse lautet `https://remote.exza.de/mcp` (Streamable HTTP). Die Geräte-PIN darf nicht als API-Schlüssel verwendet werden.
4. **Berechtigungen prüfen:** Eigenes EXZA-Konto und gekoppelten Computer auswählen. Möglichst mit `computer:read` beginnen; Schreibrechte nur bei Bedarf und mit eigener Zustimmung erteilen.
5. **Werkzeugliste prüfen:** Zuerst nur Metadaten anzeigen. Mit einer ausdrücklich autorisierten persönlichen Verbindung kann z. B. `exza_get_connection_status` getestet werden (älterer Name: `exza_status`).
6. **KI-Client verbinden:** EXZA Remote bei unterstützten ChatGPT-/Claude-/anderen MCP-Clients direkt per EXZA-OAuth einbinden. Die bloße Glama-Verzeichnisanzeige ist **noch kein Gerätezugriff**.

**Wichtig zum Datenschutz:** Das öffentliche Glama-Testprofil kann zwar Werkzeuglisten prüfen, aber keine Computerbefehle ausführen. Eine persönliche Verbindung benötigt eigene Anmeldung und Freigaben. Der optionale Glama-Gateway kann laut Betreiber komplette JSON-RPC-Aufrufe einschließlich Argumenten und Antworten protokollieren; verarbeite darüber keine vertraulichen Informationen, ohne dessen Bedingungen geprüft zu haben. EXZA, Glama und mcptry sind unabhängige Anbieter, ohne behauptete Partnerschaft.

[Datenschutzerklärung](https://remote.exza.de/legal/datenschutz) · [Nutzungsbedingungen](https://remote.exza.de/legal/nutzungsbedingungen) · [Glama-Datenschutz](https://glama.ai/policies/privacy-policy) · [Glama-AGB](https://glama.ai/policies/terms-of-service) · [Deutsche Hilfe](https://remote.exza.de/hilfe#manual-glama)

**EXZA Remote — Your computer. Your control.**
